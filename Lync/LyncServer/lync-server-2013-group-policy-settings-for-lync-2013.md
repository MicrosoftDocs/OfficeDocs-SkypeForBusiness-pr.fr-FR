---
title: Paramètres des stratégies de groupe de Lync 2013
TOCTitle: Paramètres des stratégies de groupe de Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204924(v=OCS.15)
ms:contentKeyID: 49297258
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Paramètres des stratégies de groupe de Lync 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Dans les versions précédentes de Lync et d’Office Communicator, un modèle d’administration Communicator.adm autonome était disponible pour la configuration des paramètres de stratégie de groupe du client. Pour Lync 2013, de nouveaux fichiers de modèles d’administration (fichiers .admx et .adml) sont inclus dans le modèle d’administration de stratégie de groupe Office. La disponibilité des fichiers .admx et .adml de Lync 2013 vous permet de télécharger des modèles et de gérer de manière centralisée les paramètres de stratégie de groupe de tous vos programmes et modules linguistiques Office. Pour plus d’informations, voir la description des fichiers de modèles d’administration Office 2013 (ADMX, ADML) dans la documentation Office 2013 sur [http://go.microsoft.com/fwlink/?linkid=267516\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=267516%26clcid=0x40c).

## Stratégies de démarrage du client

Vous devez configurer plusieurs stratégies de démarrage du client pour permettre aux utilisateurs de se connecter au serveur pour la première fois. Dans la mesure où ces stratégies sont appliquées avant que le client ne se connecte et commence à recevoir les paramètres de mise en service intrabande de la part du serveur, vous pouvez utiliser la stratégie de groupe pour les configurer. Pour plus d’informations, voir [Configuration des stratégies d’amorçage clientes dans Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) dans la documentation de déploiement.

