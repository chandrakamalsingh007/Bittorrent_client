# Bittorrent_client

This BitTorrent client script is designed to handle various tasks related to downloading files using the BitTorrent protocol. It starts by decoding bencoded data, the encoding format used in torrent files, allowing the extraction of essential information such as the info hash, tracker URL, piece length, and the SHA-1 hashes of the file pieces. The script can also interact with a tracker to retrieve a list of peers, decoding their IP addresses and ports for further communication. It establishes connections with peers, performs the necessary handshake, and exchanges messages to request and download specific pieces of the file. The script is capable of downloading an entire file by assembling pieces retrieved from multiple peers, verifying the integrity of each piece by comparing its hash with the expected value. This client also includes various commands to decode bencoded data, extract information from torrent files, and manage peer connections, making it a functional and modular tool for working with torrents.

<h2>Overview of the Code</h2>
Decoding Bencoded Data: The decode_bencode function handles decoding bencoded strings, integers, lists, and dictionaries.
Converting Bytes to Strings: The bytes_to_str function converts bytes objects to strings, handling lists and dictionaries recursively.
Extracting Info Hash and Pieces Hashes: These functions are used to process the torrent data, such as getting the info hash and splitting the pieces' SHA-1 hashes.
Handling Peers: The get_peers and decode_peers functions manage retrieving and decoding peer information from a tracker.
Downloading Files and Pieces: The download_file and download_piece functions handle the download of entire files or specific pieces from peers.
Running the Script
<h3>To use the script, you would run it from the command line with various commands. For example:</h3>

Decode bencoded string: python main.py decode <bencoded_string> <br>
Extract torrent info: python main.py info <torrent_file><br>
Get peers: python main.py peers <torrent_file><br>
Perform handshake: python main.py handshake <torrent_file> <peer_ip:peer_port><br>
Download file: python main.py download -o <output_file> <torrent_file><br>
Download specific piece: python main.py download_piece -o <output_file> <torrent_file> <piece_index><br>

<h4>In this repo </h4>
first:-<br>
git clone <br>
cd  Bittorrent_Client     <br>
first you have python installed <br>
pip install -r requirements.txt<br>
python main.py download -o sample.bin sample.torrent

