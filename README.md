# Stock-Prediction

**Predicting stock prices  based on people's reactions**

## Description

Based on the data from January 1st to October 31st, 2021, I predicted the fluctuation of stock prices from November 1st to November 15th, 2021.

I collected people's reaction and news. And I conducted an semantic analysis(using KoBert) with that.

## Dataset Crawling

- <a href='https://kr.investing.com/'>Investing.com(kr)</a>
- <a href='https://www.naver.com/'>Naver News</a>

## Target Stock
- Samsung Electronics Co Ltd (005930)
- Naver Corp (035420)
- Celltrion Inc (068270)

## Crawling

- Naver or Google News Crawling(naver_google.py)

```
>>> from naver_google import naver,google
>>> naver("Search Keyword")
>>> google("Search Keywork")
```

- People Reaction Crawling
```
python investing_crawling.py --START_DATE ${%Y-%m-%d} --END_DATE ${%Y-%m-%d} --company ${investing.com company name}
```

## Bert

- Pretrained Weights(Based on Naver movie Review) : <a href='https://drive.google.com/file/d/1KXaGNA_Gcpwq4Hojcf6I0civAGGFCENQ/view?usp=sharing'>Epoch 4, Train Accuracy up to 92%</a>

- Train

```
python bert_train.py --source ${Bert format txt} --save-weights-name ${Save pt name} --batch ${Batch-size}
```
- Test
```
python bert_test.py --source ${Bert format txt} --wegiths ${weight file name} --save_csv_name ${save file name} --batch ${Batch-size}
```

## Output

<a href='https://github.com/winston1214/Stock-Prediction/blob/master/PT/final_presentation.pdf'>Presentation</a>
