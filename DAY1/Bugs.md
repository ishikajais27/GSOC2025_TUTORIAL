# p5.js Bug Report: Three Subtle but Impactful Bugs

## Bug 1: WEBGL Matrix Drift in Long-Running Sketches

**What It Is**:  
In WEBGL mode, transformation matrices (e.g., `rotate()` or `translate()`) may slowly drift due to floating-point precision errors over thousands of frames, causing shapes to wobble or misalign.

**Why It’s Hard to Find**:

- Only manifests in sketches running for minutes or hours—most users test short loops.
- Subtle drift might be mistaken for intentional animation.

**Evidence**:  
No specific issue reported yet, but WEBGL’s matrix handling (touched in PR #7588) is complex and prone to precision creep in long computations.

---

## Bug 2: Mouse Event Ghosting After Canvas Resize

**What It Is**:  
After resizing the canvas with `resizeCanvas()`, mouse events (like `mouseX` or `mousePressed`) may register at old coordinates until the next frame, creating a "ghost" click offset.

**Why It’s Hard to Find**:

- Requires specific timing (resizing mid-interaction).
- Often dismissed as user error. Ties to p5.js’s event-handling quirks.

**Evidence**:  
Related to issues like #7568 (canvas state fixes), but this edge case isn’t explicitly reported.

---

## Bug 3: Shader Uniform Overflow in High-Complexity Sketches

**What It Is**:  
In WEBGL, setting too many shader uniforms (e.g., via `setUniform()`) beyond the GPU’s limit silently fails, breaking visuals without errors.

**Why It’s Hard to Find**:

- Only affects advanced users pushing dozens of uniforms.
- No clear feedback—p5.js doesn’t cap or warn about GPU limits.

**Evidence**:  
PR #7395 improved uniform handling, but overflow edge cases remain unaddressed.
