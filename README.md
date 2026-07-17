Verifico la IP

```bash
ip a
```

Script de Deploy (Completar las IP)

```bash
cd ./so-deploy
./deploy.sh -r=release -p=utils -p=kernel_scheduler -p=kernel_memory -p=cpu -p=memory_stick -p=swap -p=io -c=KERNEL_SCHEDULER_IP= -c=KERNEL_MEMORY_IP= "tp-2026-1c-Low-Cortisol"
```

Prueba Base
```bash
./kernel_memory/bin/kernel_memory ./kernel_memory/configs/base.config > ./output/kernel_memory.log 2>&1 &
./kernel_scheduler/bin/kernel_scheduler ./kernel_scheduler/configs/base.config PLANI_PRE_0.prc > ./output/kernel_scheduler.log 2>&1 &
./memory_stick/bin/memory_stick ./memory_stick/configs/base_256.config 256 > ./output/memory_stick_1.log 2>&1 &
./swap/bin/swap ./swap/swap.config > ./output/swap.log 2>&1 &
./io/bin/io ./io/io.config SLEEP > ./output/io_sleep.log 2>&1 &
./io/bin/io ./io/io.config STDIN < ./pseudocodigo/entradas_io_stdin.txt > ./output/io_stdin.log 2>&1 &
./io/bin/io ./io/io.config STDOUT > ./output/io_stdout.log 2>&1 &
./cpu/bin/cpu ./cpu/cpu.config CPU-1 > ./output/cpu_1.log 2>&1 &
```

Prueba Base con script de memoria
```bash
./kernel_memory/bin/kernel_memory ./kernel_memory/configs/base.config > ./output/kernel_memory.log 2>&1 &
./kernel_scheduler/bin/kernel_scheduler ./kernel_scheduler/configs/base.config MEMORIA_PRE_0.prc > ./output/kernel_scheduler.log 2>&1 &
./memory_stick/bin/memory_stick ./memory_stick/configs/base_256.config 256 > ./output/memory_stick_1.log 2>&1 &
./swap/bin/swap ./swap/swap.config > ./output/swap.log 2>&1 &
./io/bin/io ./io/io.config SLEEP > ./output/io_sleep.log 2>&1 &
./io/bin/io ./io/io.config STDIN < ./pseudocodigo/entradas_io_stdin.txt > ./output/io_stdin.log 2>&1 &
./io/bin/io ./io/io.config STDOUT > ./output/io_stdout.log 2>&1 &
./cpu/bin/cpu ./cpu/cpu.config CPU-1 > ./output/cpu_1.log 2>&1 &
```

Prueba PCP
```bash
./kernel_memory/bin/kernel_memory ./kernel_memory/configs/pcp.config > ./output/kernel_memory.log 2>&1 &
./kernel_scheduler/bin/kernel_scheduler ./kernel_scheduler/configs/pcp.config PCP.prc > ./output/kernel_scheduler.log 2>&1 &
./memory_stick/bin/memory_stick ./memory_stick/configs/pcp_256.config 256 > ./output/memory_stick_1.log 2>&1 &
./swap/bin/swap ./swap/swap.config > ./output/swap.log 2>&1 &
./io/bin/io ./io/io.config SLEEP > ./output/io_sleep.log 2>&1 &
./io/bin/io ./io/io.config STDIN < ./pseudocodigo/entradas_io_stdin.txt > ./output/io_stdin.log 2>&1 &
./io/bin/io ./io/io.config STDOUT > ./output/io_stdout.log 2>&1 &
./cpu/bin/cpu ./cpu/cpu.config CPU-1 > ./output/cpu_1.log 2>&1 &
```

Prueba MEM Best Fit
```bash
./kernel_memory/bin/kernel_memory ./kernel_memory/configs/pcp.config > ./output/kernel_memory.log 2>&1 &
./kernel_scheduler/bin/kernel_scheduler ./kernel_scheduler/configs/pcp.config PCP.prc > ./output/kernel_scheduler.log 2>&1 &
./memory_stick/bin/memory_stick ./memory_stick/configs/pcp_256.config 256 > ./output/memory_stick_1.log 2>&1 &
./swap/bin/swap ./swap/swap.config > ./output/swap.log 2>&1 &
./io/bin/io ./io/io.config SLEEP > ./output/io_sleep.log 2>&1 &
./io/bin/io ./io/io.config STDIN < ./pseudocodigo/entradas_io_stdin.txt > ./output/io_stdin.log 2>&1 &
./io/bin/io ./io/io.config STDOUT > ./output/io_stdout.log 2>&1 &
./cpu/bin/cpu ./cpu/cpu.config CPU-1 > ./output/cpu_1.log 2>&1 &
```

Prueba MEM Worst Fit
```bash
./kernel_memory/bin/kernel_memory ./kernel_memory/configs/mem_worst.config > ./output/kernel_memory.log 2>&1 &
./kernel_scheduler/bin/kernel_scheduler ./kernel_scheduler/configs/mem.config PLANI_MEM.prc > ./output/kernel_scheduler.log 2>&1 &
./memory_stick/bin/memory_stick ./memory_stick/configs/mem_16.config 16 > ./output/memory_stick_1.log 2>&1 &
./memory_stick/bin/memory_stick ./memory_stick/configs/mem_32.config 32 > ./output/memory_stick_2.log 2>&1 &
./memory_stick/bin/memory_stick ./memory_stick/configs/mem_64.config 64 > ./output/memory_stick_3.log 2>&1 &
./memory_stick/bin/memory_stick ./memory_stick/configs/mem_128.config 128 > ./output/memory_stick_4.log 2>&1 &
./swap/bin/swap ./swap/swap.config > ./output/swap.log 2>&1 &
./io/bin/io ./io/io.config SLEEP > ./output/io_sleep.log 2>&1 &
./io/bin/io ./io/io.config STDIN < ./pseudocodigo/entradas_io_stdin.txt > ./output/io_stdin.log 2>&1 &
./io/bin/io ./io/io.config STDOUT > ./output/io_stdout.log 2>&1 &
./cpu/bin/cpu ./cpu/cpu.config CPU-1 > ./output/cpu_1.log 2>&1 &
```

Prueba PMP
```bash
./kernel_memory/bin/kernel_memory ./kernel_memory/configs/pmp.config > ./output/kernel_memory.log 2>&1 &
./kernel_scheduler/bin/kernel_scheduler ./kernel_scheduler/configs/pmp.config PMP.prc > ./output/kernel_scheduler.log 2>&1 &
./memory_stick/bin/memory_stick ./memory_stick/configs/pmp_16_1.config 16 > ./output/memory_stick_1.log 2>&1 &
./memory_stick/bin/memory_stick ./memory_stick/configs/pmp_16_2.config 16 > ./output/memory_stick_2.log 2>&1 &
./memory_stick/bin/memory_stick ./memory_stick/configs/pmp_32.config 32 > ./output/memory_stick_3.log 2>&1 &
./memory_stick/bin/memory_stick ./memory_stick/configs/pmp_64.config 64 > ./output/memory_stick_4.log 2>&1 &
./swap/bin/swap ./swap/swap.config > ./output/swap.log 2>&1 &
./io/bin/io ./io/io.config SLEEP > ./output/io_sleep.log 2>&1 &
./io/bin/io ./io/io.config STDIN < ./pseudocodigo/entradas_io_stdin.txt > ./output/io_stdin.log 2>&1 &
./io/bin/io ./io/io.config STDOUT > ./output/io_stdout.log 2>&1 &
./cpu/bin/cpu ./cpu/cpu.config CPU-1 > ./output/cpu_1.log 2>&1 &
```

Prueba PHP
```bash
./kernel_memory/bin/kernel_memory ./kernel_memory/configs/php.config > ./output/kernel_memory.log 2>&1 &
./kernel_scheduler/bin/kernel_scheduler ./kernel_scheduler/configs/php.config PHP.prc > ./output/kernel_scheduler.log 2>&1 &
./memory_stick/bin/memory_stick ./memory_stick/configs/php_16_1.config 16 > ./output/memory_stick_1.log 2>&1 &
./memory_stick/bin/memory_stick ./memory_stick/configs/php_16_2.config 16 > ./output/memory_stick_2.log 2>&1 &
./swap/bin/swap ./swap/swap.config > ./output/swap.log 2>&1 &
./io/bin/io ./io/io.config SLEEP > ./output/io_sleep.log 2>&1 &
./io/bin/io ./io/io.config STDIN < ./pseudocodigo/entradas_io_stdin.txt > ./output/io_stdin.log 2>&1 &
./io/bin/io ./io/io.config STDOUT > ./output/io_stdout.log 2>&1 &
./cpu/bin/cpu ./cpu/cpu.config CPU-1 > ./output/cpu_1.log 2>&1 &
```
