---
title: Afficher les informations sur les périphériques de conférence
TOCTitle: Afficher les informations sur les périphériques de conférence
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994043(v=OCS.15)
ms:contentKeyID: 53095467
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Afficher les informations sur les périphériques de conférence

 

_**Dernière rubrique modifiée :** 2013-02-20_

Vous pouvez afficher des informations sur les appareils de conférence configurés pour une utilisation dans votre organisation à l’aide de Windows PowerShell et de l’applet de commande **Get-CsMeetingRoom**. Exécutez l’applet de commande **Get-CsMeetingRoom** à partir de Lync Server 2013 Management Shell ou depuis une session à distance de Windows PowerShell.

> [!NOTE]  
> Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>.

Si vous utilisez l’applet de commande **Get-CsMeetingRoom** sans aucun paramètre, elle renvoie des informations sur tous vos appareils de conférence. Les paramètres facultatifs offrent différentes manières de filtrer les informations. Pour plus d’informations, voir la section Paramètres de l’article [Get-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingRoom).


## Affichage d’informations sur tous vos appareils de conférence

  - Pour afficher des informations relatives à tous vos appareils de conférence, tapez la commande suivante dans Lync Server Management Shell et appuyez sur Entrée :
    
        Get-CsMeetingRoom
    
    Cette applet de commande renvoie des informations comme celles-ci pour chaque appareil de conférence. Notez que cet exemple montre uniquement certaines des informations affichées lors de l’exécution de cette applet de commande :
    
        ContactOptionFlags                : 64
        OwnerUrn                          : urn:device:roomsystem
        OriginatorSid                     :
        SamAccountName                    : room12129
        UserPrincipalName                 : room1219@litwareinc.com
        FirstName                         : 
        LastName                          :
        WindowsEmailAddress               :
        Sid                               : S-1-5-21-2831376166-2963252556-2165051629-1257
        LineServerURI                     :
        AudioVideoDisabled                : False
        IPPBXSoftPhoneRoutingEnabled      : False
        RemoteCallControlTelephonyEnabled : False
        PrivateLine                       :
        AcpInfo                           : {}
        HostedVoiceMail                   :
        DisplayName                       : Room 1219

## Affichage d’informations sur un appareil de conférence spécifique

  - Pour afficher des informations sur un appareil de conférence spécifique, incluez le paramètre Identity suivi de l’identité de l’appareil de conférence (en général, il s’agit du nom complet Active Directory). Par exemple :
    
        Get-CsMeetingRoom -Identity "Room 1219"

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingRoom).

