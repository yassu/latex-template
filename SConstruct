#!/usr/bin/env python
# -*- coding: utf-8 -*-


import os
import glob
from json import load as _json_load
from tempfile import NamedTemporaryFile
env = Environment(ENV = os.environ)

JSON_INFO_FILENAME = 'imgs/info.json'

def make_img_from_command(command):
    name = command['command']
    kind = command.get('type', 'text')
    arg  = command.get('arg', '')
    text = command.get('text', '')

    if "environment" not in kind:
        body = "\\%s{%s}" % (name, arg)
    else:
        body = """
        \\begin{%(name)s}
        %(text)s
        \\end{%(name)s}
        """ % {"name": name, "arg": arg, "text": text}

    if "math" in kind:
        body = "\[{}\]".format(body)

    latex_source = """
    \\documentclass{jarticle}
    \\usepackage{yassu}
    \\pagestyle{empty}
    \\begin{document}
    %s
    \\end{document}
    """ % body
    print(latex_source)

    # create source .tex file
    source = NamedTemporaryFile(mode='w+b', suffix='.tex',
                                dir='.', delete=False)
    source_dvi = os.path.splitext(source.name)[0] + '.dvi'
    source.write(latex_source.encode('utf-8'))
    output_name = 'imgs/{}.png'.format(name)
    print(output_name)
    try:
        env.Command(output_name, JSON_INFO_FILENAME,
            'platex {source} && '
            'dvipng {source_dvi} -o {out} -T tight' .format(
            source=source.name,
            out=output_name,
            source_dvi = source_dvi
        ))

    except Exception as ex:
        print('source ===')
        print('==========')
        print(latex_source)
        print(ex)
    finally:
        source.close()

info = _json_load(open(JSON_INFO_FILENAME))
for command in info:
    print(command)
    make_img_from_command(command)

env.Clean('all', 'x.log')
env.Clean('all', 'q.log')
env.Clean('all',glob.glob("tmp*.*"))
