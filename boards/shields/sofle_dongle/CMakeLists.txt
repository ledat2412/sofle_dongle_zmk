board_runner_args(nrfjprog "--nrf-family=NRF52" "--softreset")
board_runner_args(jlink "--device=nrf52" "--speed=4000")
board_runner_args(pyocd "--target=nrf52" "--frequency=4000000")

include(${ZEPHYR_BASE}/boards/common/nrfjprog.board.cmake)
include(${ZEPHYR_BASE}/boards/common/jlink.board.cmake)
include(${ZEPHYR_BASE}/boards/common/pyocd.board.cmake)
include(${ZEPHYR_BASE}/boards/common/openocd.board.cmake)

if(CONFIG_SHIELD_SOFLE_DONGLE)
    zephyr_library()
    zephyr_library_include_directories(${ZEPHYR_ZMKFIRMWARE_MODULE}/drivers)
    zephyr_library_include_directories(${ZEPHYR_BASE}/drivers)
endif() 