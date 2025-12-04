# Data Centric Programming Assignment 2025


Module: Data Centric Programming DATA2005

Course: TU850/2 – Data Science & AI

Lecturer: Bryan Duggan

Name: Prosper Umeh

Student Number: C24365571

# Screenshots

# Description of the project
This project uses real world data and applications to simulate a small library manager to rescan folders and populate the database, show statistcs, search titles, makes graphs and plot points and list tunes by book within the ABC format.
# Instructions for use

# How it works:

# List of files in the project

| Files | Source |
|-----------|-----------|
| abc_parser_app.py | Self written |
| setup_data.py | Self Written |

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

Bla bla bla


# Headings
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

So is this without specifying the language:

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












