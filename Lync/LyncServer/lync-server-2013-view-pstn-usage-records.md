---
title: 'Lync Server 2013 : Affichage des enregistrements d’utilisation RTC'
TOCTitle: Affichage des enregistrements d’utilisation RTC
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398458(v=OCS.15)
ms:contentKeyID: 49297426
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des enregistrements d’utilisation RTC dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-22_

Un enregistrement d’utilisation du réseau téléphonique commuté (RTC) spécifie une classe d’appel (interne, local ou longue distance) réalisable par différents utilisateurs, ou groupes d’utilisateurs, dans une organisation. Pour plus d’informations, reportez-vous à [Enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-pstn-usage-records.md) dans la documentation de planification.

## Pour afficher un enregistrement d’utilisation RTC via Panneau de configuration Lync Server

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Utilisation RTC**.

4.  Dans la page **Utilisation RTC**, sélectionnez l’enregistrement d’utilisation RTC que vous souhaitez afficher, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.
    
    > [!NOTE]  
    > Une page en lecture seule de l’enregistrement d’utilisation RTC sélectionné affiche les itinéraires associés et les stratégies de voix associées.

## Affichage des informations d’utilisation RTC via les applets de commande Windows PowerShell

Vous pouvez également afficher les informations d’utilisation RTC à l’aide de Windows PowerShell et de l’applet de commande **Get-CsPstnUsage**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour afficher les informations d’utilisation RTC à l’aide des applets de commande Windows PowerShell

  - Pour afficher des informations sur toutes vos utilisations RTC, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur Entrée :
    
        Get-CsPstnUsage
    
    Cette commande retourn le type d’information suivant :
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

Pour plus d’informations, reportez-vous à la section [Get-CsPstnUsage](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPstnUsage).

## Voir aussi

#### Tâches

[Créer une stratégie et voix et configurer les enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)

