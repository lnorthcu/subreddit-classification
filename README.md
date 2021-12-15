# subreddit-classification

## Data
Data not included in repo due to size constraint. To add data do the following:

1. Clone [reddit-top-2.5-million repository](https://github.com/umbrae/reddit-top-2.5-million). Store this data (2,500 csv files) inside the data/data_other folder. Next run the dataColAdder.ipynb file on the data to add the subreddit in each .csv file.
2. From data/dataGen.ipynb, run the following
```
filters = ['id', 'author', 'created_utc',
                   'domain', 'url',
                   'title', 'num_comments', 'selftext',
                  'score', 'subreddit']   
subreddit = "incels"
start_time = []
end_time = []
limit = None

df = getPosts(subreddit,start_time,end_time, filters, limit)

with open(f'data/data_incel/incel.json', 'w', encoding='utf-8') as f:
            json.dump(df, f, ensure_ascii=False, indent=4)

```

NOTE: There are two small datasets in training/ that are easy and quick to train for an example without reading in the entire dataset.

## Training
To train the model, navigate to training/ and run the train_title.ipynb.
To train a model on text data instead of title, change "title" to "text".