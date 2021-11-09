# project-function.py
# instead of using split function we can use sent_tokenize to split the sentences 
import nltk
nltk.download('punkt') 
from nltk.tokenize import sent_tokenize
s="i am a student. today is saturday. today is chaturthi? "
print(sent_tokenize(s))


#instead of using split function we can use word_tokenize to split the words
from nltk.tokenize import word_tokenize
s="i am a student.today is saturday.today is chaturthi."
print(word_tokenize(s))


# function to remove all the stopwords form the files
import nltk
nltk.download('stopwords')
from nltk.corpus import stopwords
set(stopwords.words('english'))


# used for stemmiing the words 
from nltk.stem import PorterStemmer
s= PorterStemmer() 
text="i am playing football. programers program programming languages. "
word=word_tokenize(text)
for w in word:
    print(w," after steming ",s.stem(w))
    
    
    
    # used for synonyms . in program it is used for comparing if the given search word is same as the 
# word in the file then for calculating the score we give 1 but when the search word is synonym of 
# the word in the file then we give value 0.5 or 0.1 or any values but less than 1 
# " similarity checking"
import nltk
nltk.download('wordnet')
from nltk.corpus import wordnet 
s=[]
for i in wordnet.synsets("benefit"):
    for  j in i.lemmas():
        s.append(j.name())
print(s)


# used for comparing how much the similar is the synonym with the original word 
from nltk.corpus import wordnet

syn1 = wordnet.synsets('good')[0]
syn2 = wordnet.synsets('benefit')[0]

syn1.wup_similarity(syn2)
