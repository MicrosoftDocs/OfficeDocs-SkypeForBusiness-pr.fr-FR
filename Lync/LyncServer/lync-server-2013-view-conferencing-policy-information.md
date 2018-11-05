---
title: Affichage des informations d’une stratégie de conférence
TOCTitle: Affichage des informations d’une stratégie de conférence
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49891588
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des informations d’une stratégie de conférence

 

_**Dernière rubrique modifiée :** 2013-02-23_

Dans le Panneau de configuration Lync Server 2013, les stratégies de conférence vous permettent de contrôler la manière dont la conférence est implémentée dans votre déploiement. Parmi les stratégies de conférence se trouvent :

  - une stratégie globale créée par défaut lorsque vous déployez Lync Server 2013 ;

  - une stratégie facultative au niveau du site et au niveau de l’utilisateur que vous pouvez créer et utiliser pour spécifier la manière dont la conférence est implémentée pour des sites ou utilisateurs spécifiques.

## Pour voir les paramètres de stratégie de conférence

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.

4.  Sur la page **Stratégie de conférence**, double-cliquez sur la stratégie de conférence que vous voulez voir.

5.  Dans **Modifier le filtre de fichier**, sélectionnez la case à cocher **Afficher les détails…**.
    
    **Modifier la stratégie de conférence - \<stratégie\>** s’ouvre pour afficher les paramètres pour la stratégie sélectionnée. Pour plus d’informations concernant la configuration des paramètres, voir [Création ou modification d’une stratégie de conférence dans Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) (contenu éventuellement en anglais).

## Affichage des stratégies de conférence à l’aide des cmdlets Lync Server PowerShell

Les stratégies de conférence peuvent aussi être affichées à l’aide de Lync Server PowerShell et de la cmdlet Get-CsConferencingPolicy. Celle-ci peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Affichage des stratégies de conférence

  - Pour voir les informations relatives à toutes vos stratégies de conférence, tapez la commande suivante dans Lync Server Management Shell et appuyez sur Entrée :
    
        Get-CsConferencingPolicy
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity                                  : Global
        AllowIPAudio                              : True
        AllowIPVideo                              : True
        AllowMultiView                            : True
        Description                               :
        AllowParticipantControl                   : True
        AllowAnnotations                          : True
        DisablePowerPointAnnotations              : False
        AllowUserToScheduleMeetingsWithAppSharing : True
        AllowNonEnterpriseVoiceUsersToDialOut     : False
        AllowAnonymousUsersToDialOut              : False
        AllowAnonymousParticipantsInMeetings      : True
        AllowExternalUsersToSaveContent           : True
        AllowExternalUserControl                  : False
        AllowExternalUsersToRecordMeeting         : False
        AllowPolls                                : True
        AllowSharedNotes                          : True
        EnableDialInConferencing                  : True
        EnableAppDesktopSharing                   : Desktop
        AllowConferenceRecording                  : False
        EnableP2PRecording                        : False
        EnableFileTransfer                        : True
        EnableP2PFileTransfer                     : True
        EnableP2PVideo                            : True
        AllowLargeMeetings                        : False
        EnableDataCollaboration                   : True
        MaxVideoConferenceResolution              : VGA
        MaxMeetingSize                            : 250
        AudioBitRateKb                            : 200
        VideoBitRateKb                            : 50000
        AppSharingBitRateKb                       : 50000
        FileTransferBitRateKb                     : 50000
        TotalReceiveVideoBitRateKb                : 6000
        EnableMultiViewJoin                       : True

Pour plus d’informations, voir la rubrique d’aide pour la cmdlet [Get-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsConferencingPolicy) (contenu éventuellement en anglais).

