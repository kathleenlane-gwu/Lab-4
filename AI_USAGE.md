## AI Usage

## Copilot Model
I used Copilot Chat (basic), the GPT-5 chat model, through the subscription I have through GWU.

## AI Prompt
I first asked Copilot to help me think through ideas for how to output a dataframe as a .csv file, without giving me the exact code. I entered the following prompt:
```
Give me an idea (not the actual code) for how to output a dataframe in python as a tsv file.
```

## Response: 
A simple approach is:

1. Start with your pandas DataFrame.
2. Use pandas' built-in file export method to write it to disk.
3. Specify that the field separator should be a tab character (\t) instead of a comma.
4. Decide whether you want to include:
    * the DataFrame index as the first column, or
    * only the actual data columns.
5. Save the output with a .tsv extension so it's clear that it's tab-separated.

Conceptually:

DataFrame in memory → pandas export function → tab separator → .tsv file.

A TSV file is essentially the same idea as a CSV, except tabs separate the values rather than commas. This is often useful when your text fields may contain commas, since tabs are less likely to appear in the data.

## Error
I have used to_csv() before so I figured I would try to_tsv().
```
feature_table.to_tsv("feature_table.tsv", sep="\t", index=False)
```
I then ran into this error:
```
AttributeError                            Traceback (most recent call last)
Cell In[26], line 1
----> 1 feature_table.to_tsv("feature_table.tsv", sep="\t", index=False)

File /Library/Frameworks/Python.framework/Versions/3.14/lib/python3.14/site-packages/pandas/core/generic.py:6194, in NDFrame.__getattr__(self, name)
   6190             and name not in self._accessors
   6191             and self._info_axis._can_hold_identifiers_and_holds_name(name)
   6192         ):
   6193             return self[name]
-> 6194         return object.__getattribute__(self, name)

AttributeError: 'DataFrame' object has no attribute 'to_tsv'
```

## AI Response
I first asked Copilot what this error meant, then I asked how to fix it. Copilot told me that there is no to_tsv() function in PANDAS. However, I can use the to_csv() function and specify the output as a .tsv file with tab characters as the separator. Copilot suggested I run the following code in my notebook:

```
feature_table.to_csv("feature_table.tsv", sep="\t", index=False)
```


