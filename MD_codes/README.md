sudo apt-get install grace

gmx trjcat -f step7_1.trr step7_2.trr step7_3.trr step7_4.trr step7_5.trr step7_6.trr step7_7.trr step7_8.trr step7_9.trr step7_10.trr -settime -o fixed.trr

(c)

gmx gyrate -f fixed.trr -s step7_10.tpr -o gyrate_fixedstep7.xvg

(c-alpha)

grace -nxy gyrate_fixedstep7.xvg -hdevice PNG -hardcopy -printfile gyrate_fixedstep7.png

gmx sasa -f fixed.trr -s step7_10.tpr -o sasa_fixedstep7.xvg
grace -nxy sasa_fixedstep7.xvg -hdevice PNG -hardcopy -printfile sasa_fixedstep7.png

gmx sasa -f step7_10.trr -s step7_10.tpr -o sasa_step710.xvg

grace -nxy sasa_step710.xvg -hdevice PNG -hardcopy -printfile sasa_step710.png

gmx rms -f fixed.trr -s step7_10.tpr -o rmsd_fixedstep7.xvg

grace -nxy rmsd_fixedstep7.xvg -hdevice PNG -hardcopy -printfile rmsd_fixedstep7.png

gmx rmsf -f fixed.trr -s step7_10.tpr -o rmsf_fixedstep7.xvg -res
grace -nxy rmsf_fixedstep7.xvg -hdevice PNG -hardcopy -printfile rmsf_fixedstep7.png

gmx mindist -f fixed.trr -s step7_10.tpr -n index.ndx -od mindist_fixedstep7.xvg
(group 0-1)

grace -nxy mindist_fixedstep7.xvg -hdevice PNG -hardcopy -printfile mindist_fixedstep7.png

gmx energy -f step7_10.edr -o electrostatic_fixedstep7.xvg
(9 
10)
grace -nxy electrostatic_fixedstep7.xvg -hdevice PNG -hardcopy -printfile electrostatic_fixedstep7.png

gmx hbond -f fixed.trr -s step7_10.tpr -num hbonds_chl1_fixedstep7.xvg

(protein-chl1)

grace -nxy hbonds_chl1_fixedstep7.xvg -hdevice PNG -hardcopy -printfile hbonds_chl1_fixedstep7.png

gmx hbond -f fixed.trr -s step7_10.tpr -num hbonds_popc_fixedstep7.xvg
(protein-popc)

grace -nxy hbonds_popc_fixedstep7.xvg -hdevice PNG -hardcopy -printfile hbonds_popc_fixedstep7.png

gmx hbond -f fixed.trr -s step7_10.tpr -num hbonds_pope_fixedstep7.xvg

grace -nxy hbonds_pope_fixedstep7.xvg -hdevice PNG -hardcopy -printfile hbonds_pope_fixedstep7.png

gmx hbond -f fixed.trr -s step7_10.tpr -num hbonds_sops_fixedstep7.xvg

grace -nxy hbonds_sops_fixedstep7.xvg -hdevice PNG -hardcopy -printfile hbonds_sops_fixedstep7.png

gmx hbond -f fixed.trr -s step7_10.tpr -num hbonds_sapi_fixedstep7.xvg

grace -nxy hbonds_sapi_fixedstep7.xvg -hdevice PNG -hardcopy -printfile hbonds_sapi_fixedstep7.png

gmx hbond -f fixed.trr -s step7_10.tpr -num hbonds_psm_fixedstep7.xvg

grace -nxy hbonds_psm_fixedstep7.xvg -hdevice PNG -hardcopy -printfile hbonds_psm_fixedstep7.png

cat hbonds_chl1_fixedstep7.xvg hbonds_popc_fixedstep7.xvg hbonds_pope_fixedstep7.xvg hbonds_sops_fixedstep7.xvg hbonds_sapi_fixedstep7.xvg hbonds_psm_fixedstep7.xvg > hbonds_all_lipids_fixedstep7.xvg

grace -nxy hbonds_all_lipids_fixedstep7.xvg -hdevice PNG -hardcopy -printfile hbonds_all_lipids_fixedstep7.png

