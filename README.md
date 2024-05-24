<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# Education
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
High priced education is failing. Students are going to trade and technical schools, focused on training for jobs that can earn positive return on investment. Marketing, distributing, schooling, and hiring related to trade/technical schools win.
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| ATGE | Adtalem Global Education Inc. offers professional education in various fields, including healthcare and technology, which could see increased enrollment. | chat_gpt,claude,google |
| CHGG | Chegg Inc. provides online education services, including study tools and resources, which could see increased demand as students seek alternative education paths. | chat_gpt,claude,google |
| DV | Adtalem Global Education Inc. (formerly DeVry Education Group) provides career-oriented education, including business, healthcare, and technology, likely to see increased interest. | chat_gpt |
| LIN | Lincoln Educational Services Corporation offers hands-on training in automotive, skilled trades, healthcare, and culinary fields, standing to gain from the shift. | chat_gpt |
| LOPE | Grand Canyon Education Inc. provides education services, including programs focused on professional and technical disciplines, likely to attract more students. | chat_gpt,claude,google |
| LRN | K12 Inc. offers online and blended education programs, including career technical education, which could benefit from the shift towards trade and technical schools. | chat_gpt,google |
| PRDO | Perdoceo Education Corporation focuses on postsecondary education through online, career-oriented programs, aligning well with the trend towards trade and technical education. | chat_gpt,claude |
| STRA | Strategic Education Inc. operates both online and physical campuses for professional education, potentially benefiting from increased interest in career-focused programs. | chat_gpt,claude,google |
| UTI | Universal Technical Institute Inc. provides technical education for automotive, diesel, collision repair, motorcycle, and marine technicians, directly benefiting from the trend. | chat_gpt,claude,google |
| AAPL |  | claude |
| AMZN |  | claude,google |
| APEI |  | claude,google |
| BFAM |  | claude,google |
| CECO |  | claude |
| COUR |  | claude |
| GHC |  | claude |
| GOOGL |  | claude,google |
| LAUR |  | claude |
| LINC |  | claude,google |
| META |  | claude,google |
| MSFT |  | claude,google |
| AFRM |  | twitter |
| ARM |  | twitter |
| DUOL |  | twitter |
| IOT |  | twitter |
| NVDA |  | twitter,google |
| UBER |  | twitter |
| FIS |  | google |
| ISRG |  | google |
| KHC |  | google |
| PGR |  | google |
| VST |  | google |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/education/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/education" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
