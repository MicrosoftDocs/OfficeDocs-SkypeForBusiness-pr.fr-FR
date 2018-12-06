---
title: Activation de la surveillance dans Lync Server 2013
TOCTitle: Activation de la surveillance dans Lync Server 2013
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49891268
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation de la surveillance dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-17_

Bien que les agents de collecte de données unifiée soient automatiquement installés et activés sur chaque serveur frontal, cela ne signifie pas que vous commencerez automatiquement à collecter des données de surveillance dès que vous aurez terminé l’installation de Microsoft Lync Server 2013. Auparavant, vous devez associer vos serveurs frontaux/pools frontaux à une base de données de surveillance et vous devez activer la surveillance des enregistrements des détails des appels et/ou la surveillance des données de qualité de l’expérience au niveau de l’étendue globale et/ou de l’étendue du site.

Pour obtenir des instructions pas à pas sur l’association de serveurs frontaux ou de pools frontaux à une base de données de surveillance, voir la rubrique [Association d’un magasin de surveillance à un pool frontal dans Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) dans le guide de déploiement. Ces associations créées et votre nouvelle topologie Lync Server publiée, vous ne pourrez toujours pas recueillir des données de surveillance. En effet, par défaut, à la fois l’enregistrement des détails des appels et la collecte de données QoE sont désactivés quand vous installez Lync Server 2013.

Afin de pouvoir commencer la collecte de données, vous devez activer la surveillance des enregistrements des détails des appels et/ou la surveillance des données de qualité de l’expérience. (Notez que vous n’avez pas besoin d’activer les deux types de surveillance à la fois ; si vous préférez, vous pouvez n’en activer qu’un seul.) Pour activer la surveillance des enregistrements des détails des appels au niveau global, exécutez la commande suivante dans Lync Server Management Shell :

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

Vous pouvez également activer la surveillance des enregistrements des détails des appels dans le Panneau de configuration Lync Server 2013. Dans le Panneau de configuration Lync Server, effectuez la procédure suivante :

1.  Cliquez sur **Surveillance**.

2.  Sous l’onglet **Enregistrement des détails des appels**, double-cliquez sur le paramètre **Global**.

3.  Dans le volet **Paramètre de l’enregistrement des détails des appels (CDR)**, sélectionnez **Activer la surveillance des enregistrements des détails des appels**, puis cliquez sur **Valider**.

Pour activer la surveillance QoE au niveau de la portée globale, exécutez la commande suivante à partir de Lync Server Management Shell :

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

Vous pouvez également activer la surveillance QoE à partir du Panneau de configuration Lync Server. Dans le Panneau de configuration, effectuez la procédure suivante :

1.  Cliquez sur **Surveillance**.

2.  Sous l’onglet **Données de qualité de l’expérience**, double-cliquez sur le paramètre **Global**.

3.  Dans le volet **Paramètre de qualité de l’expérience (QoE)**, sélectionnez **Activer la surveillance des données de qualité de l’expérience**, puis cliquez sur **Valider**.

Comme indiqué, les exemples précédents activent la surveillance au niveau de l’étendue globale ; ils activent les surveillances CDR et QoE dans toute votre organisation. Vous pouvez également créer des paramètres de configuration CDR et QoE distincts au niveau de l’étendue du site, puis activer ou désactiver de façon sélective la surveillance pour chaque site. Par exemple, vous pouvez activer la surveillance CDR pour votre site de Redmond et la désactiver pour votre site de Dublin. Pour plus d’informations sur la gestion des paramètres de configuration de la surveillance, voir la rubrique [Configuration des paramètres de l’enregistrement des détails des appels et de la qualité de l’expérience dans Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md) du guide de déploiement.

