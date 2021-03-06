# nlp_offenseeval

## to read list:
 * https://sites.google.com/site/offensevalsharedtask/ 
 * https://paperswithcode.com/paper/um-iuling-at-semeval-2019-task-6-identifying
 
## gameplan:
 * research approaches and what/which subtask(s) we would like to work on
 * research course material for anything useful (things richard thinks are important).
 * adapt previous nlp-assignments to be able ro read this data
 * start with a BERT model
 * Evaluate consensus of BERT models, possibly with params from top performers
 * Use macro F1 score to evalute models. (Mitigates class imbalance)
  - macro F1 = (#correct_offensive/total_offsensive + correct_unoffsensive/total_unoffsensive)/2
 * Preprocessing hashtag segmentation, emoji substitution.
 
 * Finetuning BERT with unsupervised learning
 * Spell check inccorectly spelled words and take most likely suggestion
 
 * Data representation suggestions: 
 -Hashtags have own embeddings which are concencated to BERT output.
   - gensim.downloader.load("glove-twitter-100")
   - Has embeddings for common twitter hashtags like "maga". Needs lowercased and hashtag symbol removed. 
    This can be used to concencate emb for hashtags to use domain specific information.
 -Concecate number of hashtags and number of emojis to classifier
 -Randomly initialize Hashtag/emoji embeddings and train them from OLID dataset (provided from offensEval)
    
    
 
 * Thoughts for discussion
   - Prevailance of spelling errors make the data set noisy. BERT may split up incorrectly spelled words 
     to completely unrelated words. This is a problem.
