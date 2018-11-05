---
title: Afficher des informations sur les téléphones de partie commune
TOCTitle: Afficher des informations sur les téléphones de partie commune
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994081(v=OCS.15)
ms:contentKeyID: 53095551
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Afficher des informations sur les téléphones de partie commune

 

_**Dernière rubrique modifiée :** 2013-02-20_

Vous pouvez afficher des informations sur les téléphones de partie commune configurés pour une utilisation dans votre organisation à l’aide de l’applet de commande **Get-CsCommonAreaPhone**. Exécutée sans aucun paramètre, cette applet de commande retourne des informations sur tous vos téléphones de partie commune. Les paramètres facultatifs offrent différentes manières de filtrer les informations. Par exemple, vous pouvez renvoyer tous les téléphones de partie commune qui ont des objets de contacts dans une unité d’organisation spécifiée ou tous les objets de contacts situés dans un bâtiment donné. Pour plus d’informations sur les paramètres de **Get-CsCommonAreaPhone**, voir [Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone).

Exécutez **Get-CsCommonAreaPhone** à partir de Lync Server 2013 Management Shell ou depuis une session à distance de Windows PowerShell.


## Affichage d’informations sur tous vos téléphones de partie commune

  - Pour afficher des informations sur tous vos téléphones de partie commune, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur Entrée :
    
        Get-CsCommonAreaPhone
    
    Des informations analogues aux suivantes seront retournées :
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone).

