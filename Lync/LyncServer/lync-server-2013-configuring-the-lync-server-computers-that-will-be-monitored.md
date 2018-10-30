---
title: Configuration des ordinateurs Lync Server qui seront surveillés
TOCTitle: Configuration des ordinateurs Lync Server qui seront surveillés
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205118(v=OCS.15)
ms:contentKeyID: 49298377
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des ordinateurs Lync Server qui seront surveillés

 

_**Dernière rubrique modifiée :** 2012-10-20_

Étant donné que Lync Server 2013 n’utilise pas le processus de découverte centrale utilisé dans Microsoft Lync Server 2010, chaque ordinateur Lync Server 2013 que vous souhaitez surveiller doit être capable de signaler par lui-même son existence au serveur de gestion. Pour cela, vous devez installer les fichiers d’agent Operations Manager sur chacun des ordinateurs à surveiller. Une fois les fichiers d’agent installés, vous devez configurer l’ordinateur de sorte qu’il assume la fonction de proxy System Center. Notez que ces procédures doivent être effectuées après l’installation et la configuration de Lync Server sur ces ordinateurs.

