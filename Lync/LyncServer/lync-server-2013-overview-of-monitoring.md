---
title: 'Lync Server 2013 : Vue d’ensemble de la surveillance'
TOCTitle: Vue d’ensemble de la surveillance
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204937(v=OCS.15)
ms:contentKeyID: 49891369
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble de la surveillance dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-05_

Dans Microsoft Lync Server 2013, la surveillance est utilisée pour collecter des informations d’utilisation et des données de qualité de l’expérience (QoE) sur les sessions de communication dans lesquelles vos utilisateurs sont impliqués. Une session est un terme générique qui couvre la connexion d’un utilisateur à :

  - Conférence

  - une modalité de conférence (comme l’audio/vidéo ou le partage d’application) ;

  - un autre utilisateur via une conversation P2P (comme la messagerie instantanée ou un appel audio).

> [!NOTE]  
> Lync Server 2013 fait le suivi des informations relatives à chaque session : qui a appelé qui, les points de terminaison utilisés lors de la session, la durée de la session, la qualité de la session telle qu’elle a été perçue, etc. Cependant, Lync Server n’enregistre pas et ne stocke pas l’appel à proprement parler. Il en va de même pour les conversations par messagerie instantanée : même si Lync Server enregistre des informations sur les conversations par messagerie instantanée, il ne conserve pas un enregistrement de chaque message instantané envoyé lors de la conversation.

Les informations détaillées sur l’appel collectées par Lync Server peuvent s’avérer utiles dans de nombreuses situations, notamment celles qui suivent :

  - **Retour sur investissement (ROI)** . Les administrateurs peuvent comparer les données d’utilisation collectées par le serveur de surveillance à des données semblables collectées sur leur précédent système de téléphonie afin de mettre en avant les économies réalisées et justifier le déploiement de Lync Server.

  - **Gestion des stocks de périphériques** . Les informations de gestion des actifs aident les administrateurs à identifier les anciens périphériques qui sont encore en service et qui ont besoin d’être remplacés, mais aussi à identifier les périphériques coûteux qui semblent ne pas être utilisés du tout.

  - Support technique. Les données d’identification et de résolution des problèmese permettent aux ingénieurs du support technique de déterminer la cause de l’échec d’un appel d’un utilisateur, et ce sans collecter des journaux côté serveur ou client. Ces informations sont aisément accessibles et compréhensibles par le personnel de support technique qui ne possède pas de connaissances techniques approfondies de Microsoft Lync 2013 et de Lync Server 2013.

  - **Identification et résolution des problèmes du système** . Permet aux administrateurs de détecter les problèmes majeurs qui peuvent empêcher les utilisateurs finaux d’effectuer des tâches de base comme la participation à une conférence, l’émission d’un appel ou l’envoi d’un message instantané.

Outre ces informations de base relatives aux appels, le serveur de surveillance fournit également un mécanisme qui permet aux points de terminaison SIP (par exemple, Lync 2013) de fournir des informations d’identification et de résolution des problèmes auxquelles le serveur n’a pas normalement accès :

  - **Mesures qui affectent la qualité** . Ces mesures traitent de la transmission effective de l’appel lui-même ; autrement dit, elles fournissent une sorte de carnet de voyage qui suit l’acheminement de l’appel sur le réseau. Ces mesures (qui incluent des éléments tels que la perte de paquets, la gigue et les durées d’aller-retour) fournissent des informations sur ce qui est arrivé à l’appel à partir du moment où il a quitté votre point de terminaison jusqu’à son arrivée au point de terminaison de l’autre personne.

  - **Problèmes signalés à l’utilisateur final** . Ces mesures comprennent des notifications de qualité médiocre que Lync 2013 présente aux utilisateurs finaux lorsqu’ils se trouvent trop loin d’un microphone, lorsqu’ils parlent trop doucement, lorsqu’ils disposent d’une connexion réseau médiocre ou lorsque la qualité est médiocre en raison d’un autre programme sur l’ordinateur qui consomme les ressources disponibles.

  - **Informations sur l’environnement** . Ces mesures détaillent des facteurs de qualité d’appel, notamment le type de microphone et les haut-parleurs utilisés, si l’utilisateur est connecté via une connexion VPN et si l’utilisateur utilise une connexion sans fil.

À la fin de chaque appel, les points de terminaison compatibles avec SIP transmettent automatiquement ces informations au serveur frontal ayant facilité l’appel. Aucune opération n’est nécessaire pour que les points de terminaison transmettent ces informations ; ce comportement est intégré au protocole SIP. Cependant, si vous souhaitez collecter et stocker ces informations, vous devez installer et activer la surveillance. Si vous installez et activez la surveillance, les informations relatives aux appels sont collectées par des agents exécutés sur le serveur frontal et relayées à une paire de bases de données SQL Server.

Notez que le processus d’installation et de configuration de la surveillance a été simplifié dans Lync Server 2013. Dans les versions précédentes du logiciel, la surveillance nécessitait un rôle Serveur de surveillance distinct, ce qui signifiait qu’un autre ordinateur devait généralement être réquisitionné pour servir de serveur de surveillance. Dans Lync Server 2013, le rôle Serveur de surveillance a été éliminé. Au lieu de cela, le service de surveillance (sous la forme d’« agents de collection de données unifiées ») a été colocalisé dans tous les serveurs frontaux. La colocation du service de surveillance présente au moins deux avantages majeurs :

  - Diminution du nombre de rôles serveur requis lors de l’implémentation Lync Server 2013. La décrémentation du rôle Serveur de surveillance permet également de réduire les coûts en éliminant la nécessité de maintenir des serveurs dédiés pour la surveillance.

  - Réduction de la complexité inhérente à l’installation et à l’administration de Lync Server 2013. En colocalisant les services de surveillance sur chaque serveur frontal, vous n’êtes plus obligé d’installer, de configurer et de gérer le rôle Serveur de surveillance.

Pour plus d’informations, reportez-vous à la rubrique [Déploiement du serveur de surveillance dans Lync Server 2013](lync-server-2013-deploying-monitoring.md) dans le guide de déploiement de Lync Server 2013.

