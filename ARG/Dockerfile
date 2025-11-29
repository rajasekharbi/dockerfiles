ARG VERSION
FROM almalinux:${VERSION:-9}

#again building key value pairs

ARG COURSE="DOCKER" \
    TRAINER="SIVAKUMAR"
ENV COURSE=${COURSE}
RUN echo "Trainer: ${TRAINER}, Course: ${COURSE}, Version: ${VERSION}"
CMD ["sleep", "1000"]