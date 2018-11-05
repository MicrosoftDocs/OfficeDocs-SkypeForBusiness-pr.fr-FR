---
title: Activer ou désactiver le partage de téléphone
TOCTitle: Activer ou désactiver le partage de téléphone
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994057(v=OCS.15)
ms:contentKeyID: 53095475
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activer ou désactiver le partage de téléphone

 

_**Dernière rubrique modifiée :** 2013-02-20_

Vous pouvez configurer des téléphones de partie commune en tant que *téléphones partagés* (hot-desk phones). Avec les téléphones partagés, les utilisateurs peuvent se connecter à leur propre compte d’utilisateur et, une fois connectés, utiliser les fonctionnalités Lync Server de leurs propres paramètres de profil utilisateur. Le partage de téléphone est géré à l’aide de stratégies du client : pour l’activer ou le désactiver, vous devez modifier les stratégies du client utilisées par vos téléphones de partie commune. Pour plus d’informations sur la façon de déterminer les stratégies de conférence ayant été assignées à vos téléphones de partie commune, voir [Afficher des informations sur les téléphones de partie commune](lync-server-2013-view-common-area-phone-information.md).

On utilise le paramètre EnableHotdesking de l’applet de commande **New-CSClientPolicy** ou **Set-CSClientPolicy** pour activer ou désactiver le partage de téléphone sur un téléphone de la manière suivante. Exécutez ces applets de commande depuis Lync Server 2013 Management Shell ou depuis une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).


## Activation du partage de téléphone

  - Pour activer le partage de téléphone pour un téléphone de partie commune, vous devez modifier la stratégie du client qui a été assignée à ce téléphone (ou à cette collection de téléphones).
    
    Une fois identifiée la stratégie à modifier, l’étape suivante consiste à utiliser l’applet de commande **Set-CsClientPolicy** pour affecter la valeur True au paramètre EnableHotdesking. Par exemple :
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - En guise d’alternative, vous pouvez utiliser l’applet de commande **New-CsClientPolicy** pour créer une stratégie qui active le partage de téléphone. Par exemple :
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

> [!IMPORTANT]  
> Une fois cette stratégie créée, vous devez l’assigner aux téléphones de partie communes appropriés. Pour plus d’informations, voir <a href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Assigner des stratégies à un téléphone de partie commune</a>.

## Désactivation du partage de téléphone

  - Pour désactiver le partage de téléphone pour un téléphone de partie commune, réinitialisez le paramètre EnableHotdesking de l’applet de commande **Set-CsClientPolicy** à la valeur par défaut (False). Par exemple :
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

Pour plus d’informations, voir les applets de commande New-CsNetworkSubnet et [Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy) dans la documentation [New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy).

