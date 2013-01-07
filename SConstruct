import os

env = Environment(ENV = os.environ)

VariantDir('output','source')

#custom builders which execute rst2pdf
rst2pdf = Builder(action = 'rst2pdf $SOURCE --config=conf/rst2pdf.conf -o $TARGET', suffix = '.pdf', src_suffix='.rst')
presentation = Builder(action = 'rst2pdf $SOURCE --config=conf/rst2pdf-presentation.conf -o $TARGET', suffix = '.pdf', src_suffix='.rst')

#add builders in environment
env.Append(BUILDERS = {'Rst2pdf': rst2pdf, 'Presentation': presentation})


Default(env.Rst2pdf('output/nosql', 'source/nosql'))
Default(env.Presentation('output/nosql-slides', 'source/nosql-slides'))
