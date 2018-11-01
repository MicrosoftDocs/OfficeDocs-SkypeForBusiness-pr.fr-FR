---
title: "Lync Server 2013 : (Facul.) Mod. du mappage des clés des commandes DTMF"
TOCTitle: (Facultatif) Modification du mappage des clés des commandes DTMF
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398943(v=OCS.15)
ms:contentKeyID: 49298996
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Facultatif) Modification du mappage des clés des commandes DTMF dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-30_

Les utilisateurs de conférences rendez-vous peuvent appuyer sur les touches du clavier téléphonique pour exécuter des commandes de numérotation en fréquences vocales (DTMF). Les commandes DTMF permettent aux utilisateurs qui prennent part à une conférence de contrôler les paramètres de conférence (tels que l’activation et la désactivation de leur microphone ou le verrouillage et le déverrouillage de la conférence) à l’aide du clavier de leur téléphone. Vous pouvez faire appel à des applets de commande pour modifier les touches utilisées pour les commandes DTMF. Cette étape est facultative.

> [!NOTE]  
> Pour obtenir des informations sur ces applets de commande et les options DTMF possibles, reportez-vous à la documentation Lync Server Management Shell ou l’aide de la ligne de commande Lync Server Management Shell.

## Pour modifier le mappage de touches des commandes DTMF

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou du rôle **Cs-ServerAdministrator** ou **CsAdministrator**.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez la commande suivante dans l’invite de commandes :
    
        Get-CsDialinConferencingDtmfConfiguration
    
    Cette applet de commande renvoie les paramètres DTMF utilisés pour la conférence rendez-vous.

4.  Exécutez l’applet de commande suivante et spécifiez la touche sur laquelle appuyer pour chaque option à modifier :
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    Cette applet de commande modifie les paramètres DTMF utilisés pour la conférence rendez-vous.
    
    Exemple :
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    Dans cet exemple, la touche enfoncée pour activer ou désactiver les annonces est permutée avec la touche enfoncée pour activer ou désactiver le microphone de tous les participants. Comme aucune identité n’est spécifiée, ces modifications s’appliquent aux paramètres DTMF globaux.

5.  (Facultatif) Si vous voulez créer des jeux de commandes DTMF supplémentaires pour des sites spécifiques, utilisez l’applet de commande **New-CsDialinConferencingDtmfConfiguration** avec une identité de site. Lorsque vous créez des paramètres DTMF pour des sites, les paramètres de site sont prioritaires sur les paramètres globaux. Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell ou l’aide de la ligne de commande Lync Server Management Shell.

