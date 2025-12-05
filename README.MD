# Data Centric Programming Assignment 2025


Module: Data Centric Programming DATA2005

Course: TU850/2 – Data Science & AI

Lecturer: Bryan Duggan

Name: Prosper Umeh

Student Number: C24365571

# Screenshots

![An image](images//Screenshot%202025-12-05%2005.20.28.png)


# Description of the project
This project uses real world data and applications to imulate a small library manager to rescan folders and populate the database, show statistcs, search titles, makes graphs and plot points and list tunes by book within the ABC format.
# Instructions for use

Make sure to run the setup_data.py first(source venv/bin/activate)(python setup_data.py) in your terminal as thr program needs fake folders and sample tunes to have data in the database to anaylyze. Now we run the main program(python abc_parser_app.py) and when the menu base which gives you alot of amazing options to choose from f=like plots or book titles.

# How it works:

# List of files in the project

| Files | Source |
|-----------|-----------|
| abc_parser_app.py | Self written |
| setup_data.py | Self Written |
| .gitignore   | ignore  |
# References

sqllite tutorial #1 hyperlink
Codecademy #4 hyperlink
Lab5 DCP (parsing)
parsing tutorial #5 hyperlink
Lab4
Lab 10

# What I am most proud of in the assignment

I am most proud of successfully integrating data analysis with visual presentation, specifically through the creation of the key distribution charts using Matplotlib. I was the most difficult having to bridge the gap between pandas and matplotlib, and that why I truly believe it was the most impressive, especially as I tried to run it the first time and there were major problems in my code and i was luckily able to find them in time.
    
    def __init__(self, db_name: str = "tunes.db"):
        self.conn = sqlite3.connect(db_name)

    def load_data(self) -> pd.DataFrame:
        """Loads entire SQL table into a DataFrame."""
        query = "SELECT * FROM tunes"
        return pd.read_sql(query, self.conn)
    
    def get_tunes_by_book(self, df: pd.DataFrame, book_id: int) -> pd.DataFrame:
        """Filter dataframe by book ID."""
        return df[df['book_id'] == book_id]
    
    def get_tunes_by_rhythm(self, df: pd.DataFrame, rhythm: str) -> pd.DataFrame:
        """Filter dataframe by rhythm type."""
        # Case insensitive string contains
        return df[df['rhythm'].str.contains(rhythm, case=False, na=False)]
    
    def search_tunes(self, df: pd.DataFrame, search_term: str) -> pd.DataFrame:
        """Search titles for a specific term."""
        return df[df['title'].str.contains(search_term, case=False, na=False)]

    def plot_key_distribution(self, df: pd.DataFrame) -> None:
        """Optional: Visualise the keys used in the books."""
        if df.empty:
            print("No data to plot.")
            return

        counts = df['key_sig'].value_counts().head(10) # Show top 10
        counts.plot(kind='bar', color='skyblue')
        plt.title('Distribution of Musical Keys')
        plt.xlabel('Key')
        plt.ylabel('Count')
        plt.tight_layout()
        plt.show()

# What I learned

I learned how to seperate responsibilities into distinct files (setup_data.py for creation, abc_parser_app.py for execution), demonstrating good application and helping the actual content of the files be managable showing me how great managing stuff is especially in code. I earned to read unstructured text files (the ABC notation), extract specific pieces of information (T:, R:, K:), and transform that raw data into a structured format (a Python dictionary/SQL record). And I learned the importance of user interactions and visualisatins which was achieved with the use of matplotlib ( to convert maningful numbers into plots making it easier to understand) snd building a menu interface making it easier for the user.

Headings
## Headings
#### Headings
##### Headings

This is code:

```Java
public void render()
{
	ui.noFill();
	ui.stroke(255);
	ui.rect(x, y, width, height);
	ui.textAlign(PApplet.CENTER, PApplet.CENTER);
	ui.text(text, x + width * 0.5f, y + height * 0.5f);
}
```
:

```
public void render()
{
	ui.noFill();
	ui.stroke(255);
	ui.rect(x, y, width, height);
	ui.textAlign(PApplet.CENTER, PApplet.CENTER);
	ui.text(text, x + width * 0.5f, y + height * 0.5f);
}
```

This is an image using a relative URL:

![An image](images/p8.png)

This is an image using an absolute URL:

![A different image](https://bryanduggandotorg.files.wordpress.com/2019/02/infinite-forms-00045.png?w=595&h=&zoom=2)

This is a youtube video:

[![YouTube](http://img.youtube.com/vi/J2kHSSFA4NU/0.jpg)](https://www.youtube.com/watch?v=J2kHSSFA4NU)

This is a table:

| Heading 1 | Heading 2 |
|-----------|-----------|
|Some stuff | Some more stuff in this column |
|Some stuff | Some more stuff in this column |
|Some stuff | Some more stuff in this column |

|Some stuff | Some more stuff in this column |

















