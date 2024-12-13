####################################################################################
####################################################################################
## Copyright (C) 2024 Analog Devices, Inc.
####################################################################################
####################################################################################

# All test-bench dependencies except test programs
SV_DEPS += ../../../library/utilities/utils.svh
SV_DEPS += ../../../library/drivers/dmac/dma_trans.sv
SV_DEPS += ../../../library/utilities/logger_pkg.sv
SV_DEPS += ../../../library/regmaps/reg_accessor.sv
SV_DEPS += ../../../library/vip/amd/m_axis_sequencer.sv
SV_DEPS += ../../../library/vip/amd/s_axis_sequencer.sv
SV_DEPS += ../../../library/vip/amd/m_axi_sequencer.sv
SV_DEPS += ../../../library/vip/amd/s_axi_sequencer.sv
SV_DEPS += ../../../library/drivers/dmac/dmac_api.sv
SV_DEPS += ../../../library/regmaps/adi_regmap_pkg.sv
SV_DEPS += ../../../library/regmaps/adi_regmap_dmac_pkg.sv
SV_DEPS += ../../../library/drivers/dmac/dma_trans.sv
SV_DEPS += ../../../library/utilities/test_harness_env.sv
SV_DEPS += ../../../library/regmaps/adi_peripheral_pkg.sv
SV_DEPS += environment.sv
SV_DEPS += scoreboard.sv
SV_DEPS += system_tb.sv

ENV_DEPS += system_project.tcl
ENV_DEPS += system_bd.tcl
ENV_DEPS +=../../../scripts/adi_sim.tcl
ENV_DEPS +=../../../scripts/run_sim.tcl

LIB_DEPS := axi_dmac
SIM_LIB_DEPS := io_vip

# default test program
TP := test_program

# config files should have the following format
#  cfg_<param1>_<param2>.tcl
CFG_FILES := $(notdir $(wildcard cfgs/cfg*.tcl))
#$(warning $(CFG_FILES))

# List of tests and configuration combinations that has to be run
# Format is:  <configuration>:<test name>
#TESTS := $(foreach cfg, $(basename $(CFG_FILES)), $(cfg):$(TP))
TESTS += cfg1:test_program
TESTS += cfg2_fsync:test_program
TESTS += cfg2_fsync:test_program_frame_delay
TESTS += cfg3_fsync_autorun:test_program_frame_delay

include ../../../scripts/project-sim.mk

# usage :
#
# run specific test on a specific configuration in gui mode
# 	make CFG=cfg2_fsync TST=test_program_frame_delay MODE=gui
#
# run all test from a configuration
# 	make cfg1_mm2mm_default



####################################################################################
####################################################################################
