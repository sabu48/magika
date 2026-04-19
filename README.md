# Magika

> A fork of [google/magika](https://github.com/google/magika) — AI-powered file type detection.

Magika is a novel AI-powered file type detection tool that relies on the content of files (rather than file extensions or metadata) to identify file types with high accuracy.

## Features

- **AI-powered detection**: Uses a deep learning model to identify file types
- **Fast**: Optimized for speed with minimal overhead
- **Accurate**: High precision across hundreds of file types
- **CLI & Python API**: Use from the command line or integrate into your Python projects
- **Rust bindings**: High-performance Rust implementation available

## Installation

### Python

```bash
pip install magika
```

### From source

```bash
git clone https://github.com/yourorg/magika.git
cd magika
pip install -e python/
```

## Quick Start

### CLI

```bash
magika file.pdf
magika --recursive ./directory/
magika --json file1.py file2.rs
```

### Python API

```python
from magika import Magika

m = Magika()
result = m.identify_path("document.pdf")

print(result.output.ct_label)   # e.g. "pdf"
print(result.output.score)      # confidence score (0.0 to 1.0)
print(result.output.mime_type)  # e.g. "application/pdf"
print(result.output.group)      # e.g. "document"
```

## Supported File Types

Magika supports detection of 200+ file types including:

- Documents: PDF, DOCX, XLSX, PPTX, ODT
- Code: Python, JavaScript, TypeScript, Rust, Go, Java, C/C++
- Archives: ZIP, TAR, GZIP, 7Z, RAR
- Images: PNG, JPEG, GIF, WEBP, BMP, TIFF
- Audio/Video: MP3, MP4, WAV, AVI, MKV
- Executables: ELF, PE, Mach-O
- And many more...

## Development

### Prerequisites

- Python 3.8+
- Rust (for Rust bindings)
- Docker (optional)

### Setup

```bash
# Clone the repository
git clone https://github.com/yourorg/magika.git
cd magika

# Install development dependencies
pip install -e "python/[dev]"

# Run tests
cd python && pytest tests/
```

### Docker

```bash
docker build -t magika .
docker run --rm -v $(pwd):/data magika /data/file.pdf
```

## Contributing

Contributions are welcome! Please read our contributing guidelines and open an issue or pull request.

For misdetections, please use the [misdetection issue template](.github/ISSUE_TEMPLATE/misdetection.md).

## License

Apache 2.0 — see [LICENSE](LICENSE) for details.

This project is a fork of [google/magika](https://github.com/google/magika), copyright Google LLC.
