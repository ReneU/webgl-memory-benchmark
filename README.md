# WebGL Texture Memory Benchmark

A lightweight, single-file browser tool for testing GPU memory limits by allocating WebGL textures. This benchmark helps developers understand texture memory consumption, test GPU memory boundaries, and observe WebGL context behavior under memory pressure.

⚠️ **Warning**: This tool intentionally pushes GPU memory limits and may crash your browser tab, browser process, or in extreme cases, your operating system. Use with caution and save your work before testing.

## Features

- **Flexible Texture Allocation**: Create textures of various sizes (256px to 8192px) with or without mipmaps
- **Multiple Allocation Modes**:
  - Allocate specific texture counts
  - Allocate until failure (find your GPU's limit)
  - Allocate to a target memory size with controlled rate
- **Rate Control**: Control allocation speed (1-500 MB/s) to observe gradual memory pressure
- **WebGL2 Support**: Optional `texStorage2D` API for immutable texture storage
- **Real-time Monitoring**:
  - Total allocated textures
  - Approximate memory usage (bytes, MiB)
  - Per-texture memory cost
  - GPU renderer and vendor information
  - WebGL context status
- **Context Loss Handling**: Monitors and reports WebGL context loss/restore events
- **Memory Management**: Free textures individually, in batches, or all at once

## GPU Information

The tool displays:
- `MAX_TEXTURE_SIZE`: Maximum supported texture dimension
- `MAX_TEXTURE_IMAGE_UNITS`: Number of texture units
- Renderer: GPU model (requires WEBGL_debug_renderer_info extension)
- Vendor: GPU vendor

## Limitations

- Memory estimates are approximate; actual GPU memory usage may vary
- Does not account for driver-specific compression or tiling optimizations
- Cannot measure total available VRAM (system/API limitations)
- Results depend on GPU, driver version, OS, and current system load

---

**Disclaimer**: This tool is for educational and testing purposes. The authors are not responsible for any system instability or crashes caused by using this benchmark tool.

