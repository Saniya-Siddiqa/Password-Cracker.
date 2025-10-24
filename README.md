# Password Cracker Tool

## Overview
A configurable hash cracking utility that attempts to recover a password from a given hash using either a wordlist or generated candidate passwords. Supports multiple hashing algorithms and parallel execution to accelerate the search.

## Features
- Supports common hash algorithms: MD5, SHA-1, SHA-2 family, SHA-3 family.  
- Wordlist mode: test passwords from a provided list.  
- Generate mode: brute-force passwords by generating combinations within a specified length range.  
- Multithreaded execution via ThreadPoolExecutor.  
- Progress reporting with tqdm.

## Files in this Repository
- `password_cracker.py` — main script (use as provided)  
- `wordlist.txt` — example wordlist (optional)  
- `FIG5_vscode.png` — screenshot of the tool running in VS Code (optional)

## How to Run
### Wordlist mode:
python password_cracker.py <hash_value> -w wordlist.txt --hash_type md5 --max_workers 8

shell
Copy code

### Generate (brute-force) mode:
python password_cracker.py <hash_value> --min_length 1 --max_length 3 --hash_type sha256 --max_workers 4

sql
Copy code

Replace `<hash_value>` with the target hash string. Use `--characters` to specify a custom character set if needed.

## Requirements
Install external dependency:
pip install tqdm

markdown
Copy code
(Standard libraries used: `hashlib`, `itertools`, `string`, `concurrent.futures`, `argparse`.)

## Notes & Precautions
- Only test hashes you are authorized to evaluate. Unauthorized cracking is illegal.  
- Brute-force combinations grow rapidly; choose realistic charset/length to avoid extremely long runs.  
- Monitor CPU usage when increasing `--max_workers`.
