import os

env = Environment(ENV = os.environ)

#custom builders which execute rst2pdf and rst2html
rst2pdf = Builder(action = 'rst2pdf $SOURCE --config=rst2pdf.conf -o $TARGET', suffix = '.pdf', src_suffix='.rst')
rst2html = Builder(action = 'rst2html.py $SOURCE $TARGET', suffix = '.html', src_suffix='.rst')

#add builders in environment
env.Append(BUILDERS = {'Rst2pdf': rst2pdf, 'Rst2html': rst2html})


Default(env.Rst2pdf('nosql'))
env.Rst2html('nosql')