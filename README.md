## cinesort

Simple CLI tool for linux that cleans up your movie folders a little, to the format of *Year - Title*, helping your media player not to choke on it and making it just a little prettier. Instead of just blindly moving files and breaking things, sorts everything into a pipeline so you don't accidentally lose or overwrite data.

## How it handles your files:
* **The Good:** If it's a single movie file or a folder with just one movie in it, it parses the filename, then creates a new folder or renames the parent folder appropriately.
* **The Complicated:** If a folder has multiple videos (like bonus features or multi-part files), or if the metadata is unreadable, it dumps it into a "Needs Review" list and skips it so you can check it manually.
* **The Garbage:** Leftover text files, loose subtitles, or random junk get ignored and flagged as "Pocket Lint". We all accumulate junk in all of our directories, a little reminder never hurt.

The decision to leave the file name itself intact is to allow a "master copy" to refer to. In addition, if you're in the movie folder, you know what movie you're looking at, and also sometimes that extra nonsense can be useful. Maybe you've got multiple versions of the same film (Blade Runner, looking at you).

## Setup

1. Clone it:
```
git clone https://github.com/sudoj-dev/cinesort.git
cd cinesort
```
2. Install the lone dependency - guessit
```
pip install guessit
```
Be mindful - depending on your distro, you might encounter PEP 668 and get blocked from pip install In this case, you'll need a virtual environment:
```
python3 -m venv .venv
source .venv/bin/activate
pip install guessit
```
3. Open the script and change the path to point to YOUR movies folder:
```
movies = Path("/path/to/your/movies")
```
4. Make it executable
```
chmod +x cinesort
./cinesort
```
It's as shrimple as that.
