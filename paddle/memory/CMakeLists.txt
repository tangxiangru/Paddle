add_subdirectory(detail)

cc_library(memory SRCS memory.cc)
cc_library(memcpy SRCS memcpy.cc DEPS device_context)

cc_library(paddle_memory
    DEPS
    memory
    memcpy
    meta_data
    meta_cache
    memory_block
    buddy_allocator
    system_allocator)

cc_test(memory_test SRCS memory_test.cc DEPS place paddle_memory)
