---
title: "Lync Server 2013 : Plan. de la récup. d’urgence pour le parcage d’appel"
TOCTitle: Planification de la récupération d’urgence pour le parcage d’appel
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205395(v=OCS.15)
ms:contentKeyID: 49299375
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification de la récupération d’urgence pour le parcage d’appel dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-30_

Cette section décrit certaines méthodes pour préparer la récupération d’urgence de l’application de parcage d’appel à la récupération d’urgence, et énumère certaines réflexions sur le processus de récupération d’urgence.

## Préparation à la récupération d’urgence du parcage d’appel

Gardez les informations suivantes à l’esprit lorsque vous préparez et menez à bien les procédures de récupération d’urgence.

  - Planifiez la récupération d’urgence lorsque vous effectuez votre planification de capacité. Pour les capacités de récupération d’urgence, chaque pool d’un duo de pools doit pouvoir gérer les charges de travail des services du parcage d’appel des deux pools. Pour plus d’informations sur la planification de capacité du parcage d’appel, reportez-vous à [Planification de capacité pour le parcage d’appel dans Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).

  - Durant la récupération d’urgence, les utilisateurs redirigés vers le pool de sauvegarde durant le processus de basculement utilisent le service de parcage d’appel exécuté dans le pool de sauvegarde. Par conséquent, la prise en charge de parcage d’appel durant la récupération d’urgence requiert le déploiement et l’activation l’application de parcage d’appel dans le pool principal et le pool de sauvegarde.

  - Chaque pool doit avoir une plage de numéros d’orbite valable pour que les utilisateurs hébergés dans ce pool puissent utiliser le parcage d’appels.

  - Nous vous recommandons de toujours conserver une copie de sauvegarde distincte des musiques d’attente personnalisées téléchargées pour le parcage d’appel. Ces fichiers ne sont pas sauvegardés durant le processus de récupération d’urgence de Lync Server 2013 et seront perdus si les fichiers téléchargés vers le pool sont endommagés ou effacés.

## Considérations relatives à la récupération d’urgence du parcage d’appel

Vous pouvez définir un seul ensemble de paramètres de configuration d’application de parcage d’appel et un fichier audio de musique d’attente personnalisée par pool. Ces paramètres incluent le seuil d’expiration, la musique d’attente, le nombre maximum de tentatives de prises d’appels, et l’URI d’expiration. Pour afficher ces paramètres de configuration, exécutez l’applet de commande **Get-CsCpsConfiguration**. Pour plus d’informations sur l’applet de commande **Get-CsCpsConfiguration**, reportez-vous à [Get-CsCpsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCpsConfiguration).

Durant la récupération d’urgence, parcage d’appel utilise l’application de parcage d’appel dans le pool de sauvegarde : les paramètres du pool principal ne sont donc pas sauvegardés. Si le pool principal ne peut pas être récupéré et qu’un nouveau pool est déployé pour remplacer le pool principal, les paramètres du pool principal sont perdus, et vous devez reconfigurer les paramètres du parcage d’appel, ainsi que tous les fichiers audio de musique d’attente personnalisée du nouveau pool.

Si vous déployez un nouveau pool doté d’un autre nom de domaine complet (FQDN) pour remplacer le pool principal, vous devez réaffecter l’intégralité des plages d’orbites du parcage d’appel associées au pool principal vers le FQDN du nouveau pool. Pour réaffecter les plages d’orbites au nouveau pool, vous pouvez utiliser Panneau de configuration Lync Server ou l’applet de commande **Set-CsCallParkOrbit**. Pour plus d’informations sur l’applet de commande **Set-CsCallParkOrbit**, reportez-vous à [Set-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkOrbit).

