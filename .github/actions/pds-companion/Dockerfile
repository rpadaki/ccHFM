FROM jjmerelo/alpine-raku:latest

USER root
RUN ["apk", "add", "--no-cache", "bash" \
    # workaround for https://github.com/JJ/alpine-raku/issues/24
    , "curl", "zef"]

# Install pds-companion & optional dependency
RUN curl --output pds-companion.zip -L 'https://github.com/moretrim/pds-companion/archive/0.2.0-alpha+20210317.zip' \
    && unzip pds-companion.zip                                                                                      \
    && zef install --/test Terminal::ANSIColor                                                                      \
    && cd pds-companion-*                                                                                           \
    && zef install --/test .

RUN mkdir /test
VOLUME /test
WORKDIR /test
