---
title: Affichage des numéros d’accès aux conférences rendez-vous
TOCTitle: Affichage des numéros d’accès aux conférences rendez-vous
ms:assetid: 41a7dfb4-0c89-4650-b61b-0e1bf875c62b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688037(v=OCS.15)
ms:contentKeyID: 49891324
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des numéros d’accès aux conférences rendez-vous

 

_**Dernière rubrique modifiée :** 2013-02-23_

Dans le Panneau de configuration Lync Server 2013, vous indiquez les numéros d’accès entrant pour permettre aux utilisateurs de rejoindre une réunion en externe.

## Pour afficher les numéros d’accès entrant

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Numéro d’accès entrant**.

4.  Dans la page **Numéro d’accès entrant**, cliquez sur le numéro d’accès à afficher.

5.  Dans **Modifier**, activez la case à cocher **Afficher les détails**.

## Affichage des numéros d’accès de conférence rendez-vous à l’aide des applets de commande Lync Server PowerShell

Les numéros d’accès de conférence rendez-vous peuvent aussi être affichés à l’aide de Lync Server PowerShell et de l’applet de commande Get-CsDialInConferencingAccessNumber. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Affichage des informations de configuration de la jonction SIP

  - Pour afficher des informations sur tous les numéros d’accès de conférence rendez-vous, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur Entrée :
    
        Get-CsDialInConferencingAccessNumber
    
    Les informations retournées se présentent ainsi :
    
        Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                             CN=Application Contacts,CN=RTCService=Services,
                             CN=Configuration,DC=litwareinc,DC=com
        PrimaryUri         : sip:testnumber@litwareinc.com
        DisplayName        : Test
        DisplayNumber      : 1-425-555-1019
        LineUri            : tel:+14255551019
        PrimaryLanguage    : en-US
        SecondaryLanguages : {}
        Pool               : atl-cs-001.litwareinc.com
        HostingProvider    :
        Regions            : {US}

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDialInConferencingAccessNumber).

