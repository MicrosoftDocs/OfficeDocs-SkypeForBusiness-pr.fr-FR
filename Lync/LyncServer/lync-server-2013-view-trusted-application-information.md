---
title: Affichage des informations des applications approuvées
TOCTitle: Affichage des informations des applications approuvées
ms:assetid: 7b916323-96fb-4308-bc95-c178de41a3d3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688103(v=OCS.15)
ms:contentKeyID: 49891407
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des informations des applications approuvées

 

_**Dernière rubrique modifiée :** 2015-03-30_

Utilisez la procédure suivante pour afficher les informations d’application approuvée Lync Server 2013 Management Shell dans Lync Server Management Shell.

## Affichage des informations d’application approuvée avec les applets de commande Lync Server Management Shell

Vous pouvez afficher des informations sur les applications approuvées avec Lync Server Management Shell et l’applet de commande **Get-CsTrustedApplication**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour afficher les applications approuvées

  - Pour afficher toutes les applications approuvées, tapez la commande suivante dans Lync Server Management Shell et appuyez sur Entrée :
    
        Get-CsConferenceDisclaimer
    
    Cette commande retourne des informations identiques aux suivantes pour chaque application approuvée :
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True

Pour plus d’informations, voir [Get-CsTrustedApplication](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrustedApplication).

