---
title: Affichage des paramètres de configuration des réunions
TOCTitle: Affichage des paramètres de configuration des réunions
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49891555
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des paramètres de configuration des réunions

 

_**Dernière rubrique modifiée :** 2013-02-23_

Dans le Panneau de configuration Lync Server 2013, vous pouvez utiliser le paramètre de configuration de réunion pour contrôler la façon dont les réunions sont implémentées dans votre déploiement. Cela inclut les configurations de réunion suivantes :

  - Une configuration globale créée par défaut quand vous déployez Lync Server 2013.

  - Des configurations facultatives aux niveaux du site et de l’utilisateur que vous pouvez créer et utiliser pour spécifier la façon dont les réunions sont implémentées pour des sites ou des utilisateurs spécifiques.

## Pour afficher les paramètres de configuration de réunion :

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation gauche, cliquez sur **Conférence**, puis cliquez sur **Configuration de la réunion**.

4.  Dans la page **Configuration de la réunion**, cliquez sur la configuration de réunion que vous voulez afficher.

5.  Dans **Modifier le filtre de fichiers**, cochez la case **Afficher les détails…**
    
    **Modification de la configuration de réunion - \<stratégie\>** ouvre l’affichage des paramètres pour la stratégie sélectionnée. Pour plus d’informations sur la configuration des paramètres, voir [Création ou modification d’une collection de paramètres de configuration de réunion dans Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).

## Affichage des informations de configuration de réunion à l’aide des cmdlets PowerShell Lync Server

Les paramètres de configuration de réunion peuvent également être affichés à l’aide de PowerShell pour Lync Server et de la cmdlet Get-CsMeetingConfiguration. Cette dernière peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Affichage des informations de configuration de réunion

  - Pour afficher des informations sur tous vos paramètres de configuration de réunion, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur Entrée :
    
        Get-CsMeetingConfiguration
    
    Cette action a pour effet de renvoyer des informations similaires à ce qui suit :
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

Pour plus d’informations, voir la rubrique d’aide associée à la cmdlet [Get-CsMeetingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingConfiguration).

