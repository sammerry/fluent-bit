# Build librdkafka
option(RDKAFKA_BUILD_EXAMPLES OFF)
option(RDKAFKA_BUILD_TESTS OFF)
add_subdirectory(librdkafka-0.11.3 EXCLUDE_FROM_ALL)

# librdkafka headers
include_directories(librdkafka-0.11.3/src/)

# Fluent Bit Kafka Output plugin
set(src
  kafka_config.c
  kafka_topic.c
  kafka.c)

FLB_PLUGIN(out_kafka "${src}" "rdkafka")
