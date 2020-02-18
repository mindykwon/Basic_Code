# Basic_Code

docker pull ratsgo/embedding-cpu

docker run -it --rm ratsgo/embedding-cpu bash

git pull origin master
bash preprocess.sh dump-tokenized

cd /notebooks/embedding
cat data/tokenized/wiki_ko_mecab.txt data/tokenized/ratings_mecab.txt data/tokenized/korquad_mecab.txt > data/tokenized/corpus_mecab.txt

mkdir -p /notebooks/embedding/data/word-embeddings/word2vec
python models/word_utils.py --method train_word2vec \
	--input_path /notebooks/embedding/data/tokenized/corpus_mecab.txt \
	--output_path /notebooks/embedding/data/word-embeddings/word2vec/word2vec
