---
title: "LS 2013 : (Facul.) Act. et dés. annonces indiquant ut. rejoint ou quitte conf."
TOCTitle: (Facultatif) Activation et désactivation des annonces indiquant qu’un utilisateur rejoint ou quitte une conférence
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398834(v=OCS.15)
ms:contentKeyID: 49298815
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Facultatif) Activation et désactivation des annonces indiquant qu’un utilisateur rejoint ou quitte une conférence dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-30_

Lorsque les utilisateurs d’appels entrant rejoignent ou quittent une conférence, l’application d’annonce de conférence peut annoncer ce qu’ils font en émettant une tonalité ou en prononçant leurs noms. Vous pouvez modifier le fonctionnement des annonces en exécutant des des applets de commandes. Cette étape est facultative.

## Pour modifier le comportement des annonces indiquant qu’un utilisateur rejoint ou quitte une conférence

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle **Cs-ServerAdministratorr** ou **CsAdministrator**.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez la commande suivante dans l’invite de commandes :
    
        Get-CsDialinConferencingConfiguration
    
    Cette applet de commande récupère des informations indiquant si les participants sont tenus ou non d’enregistrer leur nom en rejoignant une conférence et comment Lync Server répond lorsque des participants rejoignent ou quittent une conférence rendez-vous.

4.  Exécutez la commande suivante dans l’invite de commandes :
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **EnableNameRecording**   Détermine si des participants anonymes doivent être invités à enregistrer leur nom ou pas avant de participer à la conférence. La valeur par défaut est « $true », ce qui signifie que les participants anonymes sont invités à donner leur nom avant de participer à une conférence. (Les participants authentifiés ne sont pas tenus d’indiquer leur nom, car leur nom complet est utilisé.)
    
    **EntryExitAnnouncementsEnabledByDefault**   Indique si les annonces sont activées ou désactivées par défaut. La valeur par défaut est « $false », ce qui signifie qu’aucune annonce n’est effectuée lorsque les participants rejoignent ou quittent une conférence. Lorsqu’il planifie une réunion, l’organisateur peut ignorer ce paramètre.
    
    **EntryExitAnnouncementsType**   Indique l’action entreprise à chaque fois qu’un participant rejoint ou quitte une conférence pour laquelle les annonces ont été activées. La valeur par défaut est « UseNames », ce qui signifie qu’une annonce similaire à la suivante est effectuée : « Ken Myer a rejoint la conférence » lorsque les annonces sont activées.
    
    Vous pouvez configurer ces paramètres globalement ou au niveau d’un site. (Les paramètres configurés au niveau du site sont prioritaires sur les paramètres configurés au niveau global.)
    
    Exemple :
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    Dans cet exemple, les paramètres sont configurés au niveau du site de Redmond. Les annonces sont activées, mais les participants ne sont pas invités à donner leur nom lorsqu’ils rejoignent une conférence. Une tonalité est émise lorsque les participants rejoignent ou quittent une conférence.

