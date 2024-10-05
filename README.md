# Word Counter - Concurrent Text File Processor

This project is a concurrent word counting application that processes large text files efficiently using multithreading in Java. The application reads multiple text files in parallel and counts how many times each word appears, combining the results into a single report. It leverages Java's concurrency tools like ExecutorService, ForkJoinPool, and ConcurrentHashMap to handle large datasets with optimal performance.

## Features
- Concurrent File Processing: Efficiently processes multiple text files in parallel using multiple threads.
- Word Frequency Counting: Counts occurrences of each word across all processed files.
- Thread-Safe Data Structures: Uses ConcurrentHashMap for thread-safe storage of word counts.
- Scalable: Supports processing of large datasets by leveraging modern multithreading techniques.
- Modular Design: Easy to extend for additional text processing features.

## Technologies Used
- Java 17
- ExecutorService: To manage thread pools for concurrent file processing.
- ForkJoinPool: For parallel processing of large tasks.
- Streams API: For efficient, functional-style processing of text data.
- ConcurrentHashMap: To store word counts in a thread-safe manner.

## How It Works
1. The application reads a list of text files.
2. Each file is processed by a separate thread, which counts the frequency of each word.
3. Results are stored in a shared ConcurrentHashMap, ensuring thread safety.
4. Once all files are processed, the word counts are aggregated and displayed.

## Usage
1. Clone the repository:
```bash
git clone https://github.com/your-username/word-counter.git
cd word-counter
```
2. Compile and run the project:
```bash
javac WordCounter.java
java WordCounter
```
3. Add your text files to the project and modify the code to point to your file paths. The application will then process the files and output the word count results.

## Future Improvements
- Add support for more file formats (e.g., PDF, DOCX).
- Implement stopwords filtering.
- Add options for case-sensitive or insensitive counting.
- Add real-time progress tracking for large datasets.

## Contributing
- Feel free to contribute by submitting issues, feature requests, or pull requests!
