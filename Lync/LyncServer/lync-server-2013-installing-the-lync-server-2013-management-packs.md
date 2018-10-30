---
title: Installation des packs d’administration Lync Server 2013
TOCTitle: Installation des packs d’administration Lync Server 2013
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205202(v=OCS.15)
ms:contentKeyID: 49298645
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installation des packs d’administration Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Seul, System Center Operations Manager a la possibilité de surveiller uniquement une petite partie du système d’exploitation Windows. Toutefois, vous pouvez étendre les capacités de System Center Operations Manager en installant des packs d’administration, qui sont des logiciels déterminant les éléments que System Center Operations Manager peut surveiller, y compris la façon dont ces éléments doivent être surveillés et dont des alertes doivent être déclenchées et signalées. Microsoft Lync Server 2013 inclut deux packs d’administration System Center Operations Manager qui offrent les fonctionnalités suivantes :

  - Le pack d’administration des composants et des utilisateurs (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) assure le suivi des problèmes de Lync Server enregistrés dans des journaux des événements, enregistrés par des compteurs de performances ou consignés dans les enregistrements des détails des appels ou les bases de données de qualité de l’expérience (QoE). Concernant les problèmes critiques, System Center Operations Manager peut être configuré pour avertir immédiatement les administrateurs par courrier électronique, message instantané ou SMS (Short Message Service). La technologie des SMS est utilisée pour envoyer des messages texte d’un appareil mobile à un autre.
    
    > [!NOTE]  
    > Pour plus d’informations sur la configuration des notifications d’Operations Manager, voir Configuration des notifications dans la Bibliothèque TechNet à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=268785%26clcid=0x40c">http://go.microsoft.com/fwlink/?linkid=268785&amp;clcid=0x40C</a>.

  - Le pack de surveillance active (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) teste de façon proactive les composants Lync Server clés, comme se connecter au système, échanger des messages instantanés ou appeler un téléphone sur le réseau téléphonique commuté (TRC). Ces tests sont effectués à l’aide des applets de commande de transaction synthétique de Lync Server. Par exemple, l’applet de commande **Test-CsIM** est utilisée pour simuler une conversation de messagerie instantanée entre deux utilisateurs de test. Si la conversation de messagerie simulée échoue, une alerte est générée.

Ces deux packs d’administration fournis avec Lync Server 2013 incluent un grand nombre d’améliorations par rapport aux packs d’administration utilisés avec Microsoft Lync Server 2010. Par exemple, le pack d’administration des composants Lync Server 2013 ne se limite pas à la surveillance de Lync Server lui-même. Outre la surveillance des journaux des événements et des compteurs de performances relatifs à Lync Server, il peut également effectuer le suivi des performances et émettre des alertes pour des éléments essentiels tels que les suivants :

  - **Services Internet (IIS)**   Des alertes sont émises si les services Internet sont déconnectés. Cela est important, car les services web de Lync Server reposent sur IIS.

  - **Utilisation des processus**   Des alertes sont émises si les ressources système (telles que la mémoire disponible) commencent à devenir insuffisantes. Ces alertes sont émises même si Lync Server n’est pas responsable de l’utilisation intensive du système.

  - **Événement de défaillance de l’ordinateur**   Des alertes sont émises en cas de problème matériel ou logiciel qui menace la viabilité d’un serveur. Par exemple, les administrateurs Lync Server sont avertis si un serveur risque de subir une panne du disque dur.

Les nouveaux packs d’administration proposent également une création de rapports améliorée. Les nouveaux rapports de Lync Server 2013 sont notamment les suivants :

  - **Rapport de disponibilité des scénarios de bout en bout**   Ce rapport présente la disponibilité/durée active des services Lync Server clés tels que l’inscription ou la présence.

  - **Rapport de capacité**   Ce rapport utilise les informations du compteur de performances pour montrer les tendances des composants système, notamment la mémoire disponible et l’utilisation du processeur.

  - **Rapport de composants**   Ce rapport répertorie les principaux générateurs d’alertes regroupés par composant Lync Server.

Outre les rapports mentionnés ci-dessus, les packs d’administration de Lync Server 2013 signalent automatiquement des alertes aussi bien pour la fiabilité des appels (mesures calculées par la fonctionnalité d’enregistrement des détails des appels) que pour les états QoE (mesures calculées par la fonctionnalité de qualité de l’expérience). Si vous avez activé l’enregistrement des détails des appels, vous pouvez consulter les alertes de fiabilité des appels en effectuant la procédure suivante à partir de la console System Center Operations Manager :

  - Développez **Surveillance**, **Intégrité de Microsoft Lync Server 2013** et **Fiabilité des appels et qualité des médias**, puis cliquez sur **Fiabilité des appels**.

Pour afficher les alertes de qualité de l’expérience, effectuez la procédure suivante à partir de la console System Center Operations Manager :

  - Développez **Surveillance**, **Intégrité de Microsoft Lync Server 2013** et **Fiabilité des appels et qualité des médias**, puis cliquez sur **Qualité des médias**.

Les packs d’administration de Lync Server 2013 utilisent désormais la découverte au niveau de l’ordinateur au lieu du mécanisme de découverte centrale utilisé dans Microsoft Lync Server 2010. Cela signifie que, globalement, chaque agent System Center se découvre lui-même et signale son existence au serveur de gestion centralisée. L’utilisation de la découverte au niveau de l’ordinateur simplifie l’administration de votre infrastructure System Center, et permet la coexistence de différentes versions des packs d’administration de Lync Server (par exemple, des packs d’administration pour Lync Server 2010 et des packs d’administration pour Lync Server 2013).

