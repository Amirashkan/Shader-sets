

Uniforms

time / u_time → float, animation time in seconds
resolution / u_resolution → vec2, screen size in pixels
Must pass from your host environment (OpenGL, WebGL, etc.)

Shader Version
Desktop OpenGL → #version 330 core
WebGL2 → #version 300 es + precision highp float;
WebGL1 → omit version, use gl_FragColor for output

Fragment Output
Desktop OpenGL/WebGL2 → out vec4 fragColor;
WebGL1 → gl_FragColor = vec4(...)

Integration

uniform float u_time;
uniform vec2 u_resolution;

out vec4 fragColor;

void main() {
    vec2 uv = gl_FragCoord.xy / u_resolution.xy;
    fragColor = vec4(vec3(uv.x), 1.0);
}


Pass u_time and u_resolution from your host code for animation and scaling.

Conventions
u_ prefix for uniforms
Normalized UV coordinates (0–1) for fragments
Modular functions (random, pattern, enhanceDigitalContrast) for reuse

Notes
Designed for experimentation, not production optimization
Minor adjustments may be required for strict environment compatibility

