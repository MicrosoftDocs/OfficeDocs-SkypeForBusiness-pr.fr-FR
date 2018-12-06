---
title: "Lync Server 2013 : Vérif. de l’affect. des régions aux plans de numérotation"
TOCTitle: Vérification de l’affectation des régions aux plans de numérotation
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425903(v=OCS.15)
ms:contentKeyID: 49296972
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vérification de l’affectation des régions aux plans de numérotation Lync Server 2013

 

_**Dernière rubrique modifiée :** 2010-11-02_

Les plans de numérotation destinés aux conférences rendez-vous doivent spécifier une **région de conférence rendez-vous** pour associer les numéros d’accès aux conférences rendez-vous au plan de numérotation approprié. Lorsque vous établissez un plan de numérotation, vous spécifiez la région de conférence rendez-vous qui s’applique au plan de numérotation. Ensuite, lorsque vous créez le numéro d’accès à la conférence rendez-vous, vous sélectionnez les régions qui associent le numéro d’accès aux plans de numérotation appropriés.

Comme il est important de spécifier une région pour tous les plans de numérotation, nous vous recommandons d’utiliser cette procédure pour vérifier que tous les plans de numérotation sont associés à des régions. Cette étape est facultative.

Utilisez l’applet de commande **Get-CsDialPlan** pour vérifier qu’une région est configurée pour tous les plans de numérotation de conférence rendez-vous. Si ce n’est pas le cas, vous pouvez utiliser l’applet de commande **Set-CsDialPlan** pour configurer la région. Vous pouvez également utiliser le Panneau de configuration Lync Server pour mettre à jour dans les plans de numérotation existant. Pour plus d’informations sur l’utilisation du Panneau de configuration Lync Server, reportez-vous à [Modification d’un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

## Pour vérifier que la région est correctement configurée dans les plans de numérotation

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle **Cs-VoiceAdministrator** , **Cs-ServerAdministrator** ou **CsAdministrator** .

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez la commande suivante dans l’invite de commandes :
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    Exemple :
    
        Get-CsDialPlan
    
    Dans cet exemple, tous les plans de numérotation configurés pour votre organisation sont renvoyés.

4.  Vérifiez les plans de numérotation renvoyés pour identifier ceux ne comportant pas la région de conférence rendez-vous. Pour plus d’informations, reportez-vous à la documentation relative à Lync Server Management Shell.

## Pour définir la propriété de région d’un plan de numérotation

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle **Cs-VoiceAdministrator** , **Cs-ServerAdministrator** ou **CsAdministrator** .

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Pour tous les plans de numérotation ne comportant pas de région de conférence rendez-vous, exécutez :
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    Exemple :
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    Dans cet exemple, le plan de numérotation dont l’identité est Redmond est modifié afin de définir la propriété DialinConferencingRegion sur « US West Coast ». Pour plus d’informations, reportez-vous à la documentation relative à Lync Server Management Shell.

