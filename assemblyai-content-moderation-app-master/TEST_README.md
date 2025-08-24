# Test Documentation

## Running Tests

To run the unit tests for this project:

```bash
# Run tests
python -m pytest test_utilities.py -v

# Run tests with coverage report
python -m pytest test_utilities.py --cov=utilities --cov-report=term-missing

# Run tests with HTML coverage report
python -m pytest test_utilities.py --cov=utilities --cov-report=html
```

## Test Coverage

The test suite covers all lines of code in `utilities.py` with 100% coverage, including:

### Covered Areas:
- **get_yt() function**: Tests YouTube video download functionality
- **transcribe_yt() function**: Comprehensive coverage including:
  - File reading and chunking (lines 35-40)
  - File operations (txt/srt writing, lines 99-101, 117-118)
  - ZIP file creation (lines 120-123)
  - File cleanup operations (lines 126-132)
  - Transcription polling loop (lines 84-86)
  - API interactions with AssemblyAI
  - Error handling and edge cases

### Test Structure:
- Uses pytest framework with mocking for external dependencies
- Mocks Streamlit UI components, API calls, and file operations
- Tests both happy path scenarios and edge cases
- Verifies file operations work correctly with real file system operations

### Key Features Tested:
1. **Chunked file reading**: Ensures large audio files are processed in chunks
2. **File format handling**: Tests txt, srt, and zip file creation
3. **Cleanup operations**: Verifies proper file cleanup after processing
4. **API integration**: Tests interaction with AssemblyAI API endpoints
5. **Polling mechanism**: Tests the transcription status polling loop

All previously uncovered "red lines" now have comprehensive test coverage.