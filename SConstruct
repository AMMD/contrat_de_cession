my_sources=['main.tex', 'config.tex', 'lal.tex', 'texte_lal.tex']

import os
env = Environment(ENV=os.environ)
texformalizer = Builder(action='texformalize $SOURCES')
env.Append(BUILDERS = {'TeXFormalizer' : texformalizer})
formalisons = env.TeXFormalizer(source=my_sources)
Depends(formalisons,my_sources)

pdfOutput = env.PDF(target='contrat_cession.pdf',source='main.tex')
Depends(pdfOutput,formalisons)
