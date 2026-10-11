# Change log

## 2026-10-11 — Retarget flow from IHP SG13G2 to SG13CMOS5L

The competition requires the IHP CMOS5L process and the `cmos5l` branch of
`TinyTapeout/ttihp-verilog-template`. The repo had been created from the default
(SG13G2, `ttihp26b`) template, so CI was hardening and gate-level-testing on the wrong PDK.

- `.github/workflows/{gds,docs,fpga}.yaml`: `tt-gds-action@ttihp26b` → `@ihp-cmos5l`,
  `pdk: ihp-sg13g2` → `ihp-sg13cmos5l`.
- `test/Makefile`: gate-level sim cell models now come from `ihp-sg13cmos5l/libs.ref/sg13cmos5l_{io,stdcell}`.
- `src/config.json`: PDN settings from the CMOS5L template (`FP_PDN_VPITCH` 50.0, `FP_PDN_VWIDTH` 2.1).
- `.devcontainer/Dockerfile`: `PDK=ihp-sg13cmos5l`; tt-support-tools branch, LibreLane version, and
  IHP-Open-PDK revision pinned to match `tt-gds-action@ihp-cmos5l`; PDK installed from IHP-Open-PDK
  because CMOS5L is not distributed through ciel. (The upstream CMOS5L template still ships the
  SG13G2 devcontainer.)
- Kept `test.yaml`'s `python -m cocotb_tools.check_results` (cocotb 2.0.1) over the template's
  `grep failure` check.
