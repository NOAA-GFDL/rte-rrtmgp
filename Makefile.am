lib_LTLIBRARIES = librte.la librrtmgp.la

#RTE solver library.
rte_frontend = $(top_srcdir)/rte-frontend
rte_kernels = $(top_srcdir)/rte-kernels
librte_la_SOURCES = $(rte_frontend)/mo_fluxes.F90 \
                    $(rte_frontend)/mo_optical_props.F90 \
                    $(rte_frontend)/mo_rte_config.F90 \
                    $(rte_frontend)/mo_rte_kind.F90 \
                    $(rte_frontend)/mo_rte_lw.F90 \
                    $(rte_frontend)/mo_rte_sw.F90 \
                    $(rte_kernels)/mo_rte_util_array.F90 \
                    $(rte_frontend)/mo_source_functions.F90 \
                    $(rte_kernels)/mo_fluxes_broadband_kernels.F90 \
                    $(rte_kernels)/mo_optical_props_kernels.F90 \
                    $(rte_kernels)/mo_rte_solver_kernels.F90 \
                    $(rte_frontend)/mo_rte_util_array_validation.F90
$(rte_frontend)/mo_fluxes.lo: $(rte_frontend)/mo_rte_kind.lo \
                              $(rte_kernels)/mo_fluxes_broadband_kernels.lo \
                              $(rte_frontend)/mo_optical_props.lo \
                              $(rte_kernels)/mo_rte_util_array.lo
$(rte_frontend)/mo_optical_props.lo: $(rte_frontend)/mo_rte_kind.lo \
                                     $(rte_frontend)/mo_rte_config.lo \
                                     $(rte_kernels)/mo_rte_util_array.lo \
                                     $(rte_frontend)/mo_rte_util_array_validation.lo \
                                     $(rte_kernels)/mo_optical_props_kernels.lo
$(rte_frontend)/mo_rte_lw.lo: $(rte_frontend)/mo_rte_kind.lo \
                              $(rte_kernels)/mo_rte_util_array.lo \
                              $(rte_frontend)/mo_optical_props.lo \
                              $(rte_frontend)/mo_source_functions.lo \
                              $(rte_frontend)/mo_fluxes.lo \
                              $(rte_kernels)/mo_rte_solver_kernels.lo
$(rte_frontend)/mo_rte_sw.lo: $(rte_frontend)/mo_rte_kind.lo \
                              $(rte_kernels)/mo_rte_util_array.lo \
                              $(rte_frontend)/mo_optical_props.lo \
                              $(rte_frontend)/mo_source_functions.lo \
                              $(rte_frontend)/mo_fluxes.lo \
                              $(rte_kernels)/mo_rte_solver_kernels.lo
$(rte_kernels)/mo_rte_util_array.lo: $(rte_frontend)/mo_rte_kind.lo
$(rte_frontend)/mo_source_functions.lo: $(rte_frontend)/mo_rte_kind.lo \
                                        $(rte_frontend)/mo_optical_props.lo
$(rte_kernels)/mo_fluxes_broadband_kernels.lo: $(rte_frontend)/mo_rte_kind.lo
$(rte_kernels)/mo_optical_props_kernels.lo: $(rte_frontend)/mo_rte_kind.lo
$(rte_kernels)/mo_rte_solver_kernels.lo: $(rte_frontend)/mo_rte_kind.lo
$(rte_frontend)/mo_rte_util_array_validation.lo: $(rte_frontend)/mo_rte_kind.lo


#RRTMGP gas optics library.
rrtmgp_frontend = $(top_srcdir)/rrtmgp-frontend
rrtmgp_kernels = $(top_srcdir)/rrtmgp-kernels
gas_optics = $(top_srcdir)/gas-optics
librrtmgp_la_SOURCES = $(gas_optics)/mo_gas_concentrations.F90 \
                       $(gas_optics)/mo_gas_optics.F90 \
                       $(rrtmgp_frontend)/mo_gas_optics_rrtmgp.F90 \
                       $(gas_optics)/mo_gas_optics_constants.F90 \
                       $(gas_optics)/mo_gas_optics_util_string.F90 \
                       $(rrtmgp_kernels)/mo_gas_optics_rrtmgp_kernels.F90 \
                       $(top_srcdir)/examples/mo_load_coefficients.F90 \
                       $(top_srcdir)/extensions/mo_heating_rates.F90
librrtmgp_la_LIBADD = $(top_builddir)/librte.la
$(gas_optics)/mo_gas_concentrations.lo: $(gas_optics)/mo_gas_optics_util_string.lo
$(gas_optics)/mo_gas_optics.lo: $(gas_optics)/mo_gas_concentrations.lo
$(rrtmgp_frontend)/mo_gas_optics_rrtmgp.lo: $(gas_optics)/mo_gas_optics_constants.lo \
                                            $(gas_optics)/mo_gas_optics_util_string.lo \
                                            $(rrtmgp_kernels)/mo_gas_optics_rrtmgp_kernels.lo \
                                            $(gas_optics)/mo_gas_concentrations.lo \
                                            $(gas_optics)/mo_gas_optics.lo
$(top_srdir)/extensions/mo_heating_rates.lo: $(gas_optics)/mo_gas_optics_constants.lo

include_HEADERS = mo_fluxes.mod \
                  mo_optical_props.mod \
                  mo_rte_config.mod \
                  mo_rte_kind.mod \
                  mo_rte_lw.mod \
                  mo_rte_sw.mod \
                  mo_rte_util_array.mod \
                  mo_source_functions.mod \
                  mo_fluxes_broadband_kernels.mod \
                  mo_optical_props_kernels.mod \
                  mo_rte_solver_kernels.mod \
                  mo_rte_util_array_validation.mod \
                  mo_gas_concentrations.mod \
                  mo_gas_optics.mod \
                  mo_gas_optics_rrtmgp.mod \
                  mo_gas_optics_constants.mod \
                  mo_gas_optics_util_string.mod \
                  mo_gas_optics_rrtmgp_kernels.mod \
                  mo_load_coefficients.mod \
                  mo_heating_rates.mod

CLEANFILES = *.mod
