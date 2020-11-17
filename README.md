# gelget
Gelbooru scrapper written in perl

## Description

Gelget is a gelbooru scrapper with a modest set of features. It can automatically form and send a request for XML to parse and then download images.

### Dependencies:

* perl5 (tested on 5.30.3)
* File::HomeDir
* File::Fetch
* Getopt::Long
* XML::Twig (tested on 3.520)

Besides XML::Twig all modules should already be included in base perl installation

### Configuration

Gelget can automatically add api_key and user_id to request.

Simply put:\
api_key=your_api_key\
user_id=your_user_id

into file called .gelget in your home directory

### Usage

	-h --help               show this menu and exit
	-v --version            show version and exit
	-n --number             show only the amount of images that query will match and exit
	-o --overwrite		overwrite downloaded images instead of skipping over them
	-q --quiet              suppress some messages from showing up
	-t --tags               tags to include in query
	-e --excluded_tags      tags to exclude from query
	-S --safe               equivalent of --tags "rating:safe"
	-Q --questionable       equivalent of --tags "rating:questionable"
	-E --explicit           equivalent of --tags "rating:explicit"
	-l --limit              maximum number of images to include in query
	-p --page               page to get results from, essentially works as an offset
	--pages                 download images from page 0 till specified
	-a --api-key            set api_key to use in query
	-u --user-id            set user_id to use in query

### Example

retrieve 20 images from page 0 with specified tags

    gelget -l 20 -p 0 -t 'your tags'
