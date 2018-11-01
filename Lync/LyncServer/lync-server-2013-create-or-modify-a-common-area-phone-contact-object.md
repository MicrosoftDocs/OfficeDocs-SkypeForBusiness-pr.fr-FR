---
title: Créer ou modifier un objet contact téléphonique de partie commune
TOCTitle: Créer ou modifier un objet contact téléphonique de partie commune
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994083(v=OCS.15)
ms:contentKeyID: 53095558
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer ou modifier un objet contact téléphonique de partie commune

 

_**Dernière rubrique modifiée :** 2013-02-20_

Pour créer des objets contact services de domaine Active Directory pour tous vos téléphones de partie commune, utilisez l’applet de commande **New-CsCommonAreaPhone**. Cette applet de commande peut créer de nouveaux objets contact en vue de les utiliser avec des téléphones de partie commune ou associer des objets contact existants à un nouveau téléphone de partie commune. Pour modifier les propriétés des objets contact associés aux téléphones de partie commune, utilisez l’applet de commande **Set-CsCommonAreaPhone**. Les paramètres facultatifs pour **Set-CsCommonAreaPhone** vous permettent de modifier des éléments, tels que le nom d’affichage Active Directory du contact ou l’URI associé au téléphone, et d’activer et de désactiver le compte à utiliser avec Lync Server. Pour plus d’informations sur les modifications disponibles, voir la section Paramètres à l’adresse [Set-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCommonAreaPhone). Pour plus d’informations sur les paramètres **New-CsCommonAreaPhone**, voir [New-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCommonAreaPhone).

Vous pouvez exécuter ces deux applets de commande à partir de Lync Server 2013 Management Shell ou d’une sessions à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).


## Création d’un objet contact de téléphone de partie commune

  - Pour créer un objet contact de téléphone de partie commune, utilisez l’applet de commande **New-CsCommonAreaPhone**. Au minimum, vous devez fournir les informations suivantes quand vous créez un objet contact :
    
      - **LineUri** : le numéro de téléphone assigné au téléphone de partie commune. Notez que vous devez utiliser le format E.164 lorsque vous spécifiez ce numéro de téléphone.
    
      - **RegistrarPool** : le nom de domaine complet (FQDN) du pool de serveurs d’inscriptions qui hébergera l’objet contact.
    
      - **OU** : le nom unique du conteneur Active Directory dans lequel l’objet contact sera créé.
    
    Nous recommandons également de fournir un nom d’affichage services de domaine Active Directory. Dans le cas contraire, vous devrez utiliser un GUID pour spécifier l’identité du téléphone. Par exemple :
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

## Modification d’un objet contact de téléphone de partie commune

  - Pour modifier les propriétés d’un objet contact de téléphone de partie commune existant, utilisez l’applet de commande **Set-CsCommonAreaPhone**. Par exemple, cette commande configure l’adresse SIP pour le téléphone de partie commune avec DisplayName Lobby :
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

Pour plus d’informations, voir les rubriques d’aide pour l’applet de commande [New-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCommonAreaPhone) et l’applet de commande [Set-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCommonAreaPhone).

