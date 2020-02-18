# Basic_Code

docker pull ratsgo/embedding-cpu
docker run --rm ratsgo/embedding-cpu bash
mkdir -p /notebooks/embedding/data/word-embeddings/lsa
python models/word_utils.py --method latent_semantic_analysis \
	--input_path /notebooks/embedding/data/tokenized/for-lsa-mecab.txt \
	--output_path /notebooks/embedding/data/word-embeddings/lsa/lsa
