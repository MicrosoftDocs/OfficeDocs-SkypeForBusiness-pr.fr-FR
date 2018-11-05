---
title: "Temps de récup. nécessaire pr basc. et rest. les pools dans Lync Server 2013"
TOCTitle: Temps de récupération nécessaire pour basculer et restaurer les pools
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205079(v=OCS.15)
ms:contentKeyID: 49298059
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Temps de récupération nécessaire pour basculer et restaurer les pools dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-10_

Pour le basculement de pool et la restauration de pool, le but à atteindre pour la durée maximale d’interruption admissible (RTO) est de 30 minutes. Il s’agit de la durée nécessaire pour que le basculement ait lieu, une fois que les administrateurs ont identifié une panne et lancé les procédures de basculement. Cette durée ne comprend pas le temps nécessaire aux administrateurs pour évaluer la situation et prendre une décision, ni le temps nécessaire aux utilisateurs pour se connecter une fois le basculement terminé.

Pour le basculement de pool et la restauration de pool, le but à atteindre pour la perte de données maximale admissible (RPO) est de 30 minutes. Cela représente une mesure en temps des données qui pourraient être perdues en raison de la panne, en raison de la latence de réplication du service de sauvegarde. Par exemple, si un pool connaît une défaillance à 10 h 00, et que le RPO est de 30 minutes, les données écrites dans ce pool entre 9 h 30 et 10 h 00 peuvent ne pas avoir été répliquées sur le pool de sauvegarde et seront perdues.

Les chiffres de RTO et de RPO de ce document considèrent que les deux centres de données sont situés dans la même région du monde avec un transport haute vitesse à faible latence entre les deux sites. Ces chiffres sont mesurés pour un pool avec 40 000 utilisateurs actifs et 200 000 utilisateurs activés pour Lync par rapport à un modèle utilisateur prédéfini pour lequel il n’y a pas de journal des travaux en souffrance dans la réplication des données. Ces chiffres peuvent changer en fonction du test et de la validation des performances.

