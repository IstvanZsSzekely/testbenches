####################################################################################
####################################################################################
## Copyright 2024(c) Analog Devices, Inc.
####################################################################################
####################################################################################

# All test-bench dependencies except test programs
SV_DEPS += ../../../library/utilities/utils.svh
SV_DEPS += ../../../library/utilities/logger_pkg.sv
SV_DEPS += ../../../library/regmaps/reg_accessor.sv
SV_DEPS += ../../../library/vip/amd/m_axis_sequencer.sv
SV_DEPS += ../../../library/vip/amd/s_axis_sequencer.sv
SV_DEPS += ../../../library/vip/amd/m_axi_sequencer.sv
SV_DEPS += ../../../library/vip/amd/s_axi_sequencer.sv
SV_DEPS += ../../../library/utilities/test_harness_env.sv
SV_DEPS += ../../../library/regmaps/adi_peripheral_pkg.sv
SV_DEPS += ../../../library/regmaps/adi_regmap_pkg.sv
SV_DEPS += ../../../library/drivers/common/mailbox.sv
SV_DEPS += ../../../library/drivers/common/x_monitor.sv
SV_DEPS += ../../../library/drivers/common/scoreboard.sv
SV_DEPS += ../../../library/drivers/common/watchdog.sv
SV_DEPS += environment.sv
SV_DEPS += system_tb.sv

ENV_DEPS += system_project.tcl
ENV_DEPS += system_bd.tcl
ENV_DEPS += ../../../scripts/adi_sim.tcl
ENV_DEPS += ../../../scripts/run_sim.tcl

# default test program
TP := test_program

# config files should have the following format
#  cfg_<param1>_<param2>.tcl
CFG_FILES := $(notdir $(wildcard cfgs/cfg*.tcl))
#$(warning $(CFG_FILES))

# List of tests and configuration combinations that has to be run
# Format is:  <configuration>:<test name>
TESTS := $(foreach cfg, $(basename $(CFG_FILES)), $(addprefix $(cfg):, $(TP)))
#TESTS += cfg1:test_program

include ../../../scripts/project-sim.mk

# usage :
#
# run specific test on a specific configuration in gui mode
# 	make CFG=cfg2_fsync TST=test_frame_delay MODE=gui
#
# run all test from a configuration
# 	make cfg1_mm2mm_default

####################################################################################
####################################################################################
