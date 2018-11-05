---
title: 'Lync Server 2013 : Configuration de la stratégie de conférence rendez-vous'
TOCTitle: Configuration de la stratégie de conférence rendez-vous
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398810(v=OCS.15)
ms:contentKeyID: 49298343
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la stratégie de conférence rendez-vous dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-03-21_

Une stratégie de conférence est un paramètre de compte d’utilisateur qui spécifie les modalités de la conférence pour les participants. Vous pouvez créer des stratégies de conférence avec une étendue de site ou d’utilisateur. Les paramètres de stratégie de conférence englobent de nombreux aspects de la planification de la conférence et de la participation. Plusieurs paramètres de stratégies de conférence prennent en charge la conférence rendez-vous pour les participants. Lorsque vous configurez une conférence rendez-vous, vous devez vérifier que ces champs sont correctement définis pour votre organisation, et vous devez les modifier uniquement en cas de nécessité.

Vérifiez les champs suivants dans votre stratégie de conférence :

  - **Autoriser les participants à inviter des utilisateurs anonymes**    Ce paramètre autorise les organisateurs de réunion à inviter des participants anonymes (c’est-à-dire non authentifiés) aux réunions. Ce paramètre est facultatif pour la conférence rendez-vous. Il est sélectionné par défaut dans la stratégie de conférence globale par défaut.

  - **Activer la conférence rendez-vous RTC**    Ce paramètre autorise des utilisateurs à participer à la partie audio d’une conférence en composant un numéro à partir du réseau téléphonique commuté. Ce paramètre est obligatoire pour la conférence rendez-vous. Il est sélectionné par défaut dans la stratégie de conférence globale par défaut.

  - **Autoriser l’accès sortant des participants anonymes**    Ce paramètre autorise les utilisateurs anonymes qui participent déjà à la réunion à participer à la partie audio de la conférence en utilisant un appel sortant. Ce paramètre est facultatif pour la conférence rendez-vous. Il n’est pas sélectionné par défaut dans la stratégie de conférence globale par défaut.

  - **Autoriser l’accès sortant des participants non-Voix Entreprise**   Ce paramètre autorise les organisateurs et les participants aux réunions non activés pour Voix Entreprise à participer au volet audio de la conférence en utilisant un appel sortant. Celui-ci est autorisé en fonction de la stratégie de voix affectée à l’organisateur. Il n’est pas sélectionné par défaut dans la stratégie de conférence globale par défaut. Sa valeur par défaut est désactivée.
    
    > [!NOTE]  
    > Pour activer cette fonctionnalité, une stratégie de voix appropriée doit être affectée à un organisateur de réunion non activé pour Voix Entreprise afin d’autoriser les appels sortants depuis une conférence qu’il aura organisée. Il est possible d’affecterr une stratégie de voix à un utilisateur non activé pour Voix Entreprise depuis Lync Server Management Shell. Si aucune stratégie de voix n’est explicitement affectée à l’utilisateur, la stratégie de voix globale est employée pour autoriser la demande d’appel sortant. Cette stratégie est également appliquée en l’absence de stratégie de voix de site. 

La procédure de cette section explique comment modifier la stratégie de conférence. Pour plus d’informations sur la façon de configurer tous les paramètres qui définissent l’expérience des participants dans la stratégie de conférence par défaut, reportez-vous à [Création ou modification d’une collection de paramètres de configuration de réunion dans Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md). Pour plus d’informations sur la façon de créer une stratégie de conférence pour un utilisateur ou un groupe d’utilisateurs spécifique, reportez-vous à [Création ou modification d’une stratégie de conférence dans Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md). Pour obtenir une liste de tous les paramètres de stratégie de conférence disponibles, reportez-vous à [Référence des paramètres de stratégie de conférence pour Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

## Pour modifier la stratégie de conférence rendez-vous

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle **Cs-ServerAdministratorr** ou **CsAdministrator** .

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**.

4.  Sous l’onglet **Stratégie de conférence** , double-cliquez sur un nom de stratégie de conférence pour ouvrir la boîte de dialogue **Modifier la stratégie de conférence** .

5.  Vérifiez que les champs de la conférence rendez-vous correspondent à votre organisation et modifiez les paramètres, le cas échéant.

6.  Cliquez sur **Valider** .

