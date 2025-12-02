
VeriRISC CPU
Implementazione RTL in Verilog di una CPU a 8-bit basata su accumulatore con set di istruzioni ridotto (RISC). Il progetto include il design completo, la verifica tramite testbench e gli script di sintesi.
Caratteristiche Tecniche
 * Architettura: Bus dati a 8 bit, bus indirizzi a 5 bit (spazio di indirizzamento di 32 parole).
 * Memoria: Architettura a doppia porta (Dual-Port) che permette fetch ed esecuzione in un singolo ciclo di clock.
 * Controllo: Macchina a stati finiti (FSM) sincronizzata sul fronte di salita del clock.
Componenti Principali
 * ALU: Esegue operazioni aritmetiche (ADD) e logiche (AND, XOR).
 * Registri: Accumulatore (AC), Registro Istruzioni (IR), Program Counter (PC).
 * Controller: Genera i segnali di controllo decodificando l'opcode e lo stato della fase.
 * Multiplexer Indirizzi: Seleziona tra il Program Counter (fetch) e il campo indirizzo dell'istruzione (execute).
Instruction Set Architecture (ISA)
Il processore utilizza un opcode a 3 bit per supportare 8 istruzioni.
| Opcode | Mnemonic | Descrizione |
|---|---|---|
| 000 | HLT | Arresta l'esecuzione della CPU. |
| 001 | SKZ | Salta l'istruzione successiva se AC = 0. |
| 010 | ADD | Somma il contenuto della memoria all'Accumulatore. |
| 011 | AND | Esegue AND logico tra Memoria e Accumulatore. |
| 100 | XOR | Esegue XOR logico tra Memoria e Accumulatore. |
| 101 | LDA | Carica il dato dalla memoria nell'Accumulatore. |
| 110 | STO | Salva il contenuto dell'Accumulatore in memoria. |
| 111 | JMP | Salto incondizionato all'indirizzo specificato. |
Quick Start
Simulazione
Per simulare il design e i test diagnostici (CPUtest1, CPUtest2, CPUtest3) utilizzando Cadence Xcelium:
xrun -f filelist.txt -access +rwc

Sintesi
Per eseguire la sintesi logica del design utilizzando Cadence Genus:
genus -f genus_script.tcl

