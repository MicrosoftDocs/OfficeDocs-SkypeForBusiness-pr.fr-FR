---
title: Configurer une application SNMP
TOCTitle: Configurer une application SNMP
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412972(v=OCS.15)
ms:contentKeyID: 49298796
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurer une application SNMP

 

_**Dernière rubrique modifiée :** 2012-10-03_

Lync Server 2013 intègre une interface de service web standard qui vous permet de connecter le service d’informations sur l’emplacement aux applications SNMP (Simple Network Management Protocol) qui associent des adresses MAC aux ports et commutateurs.

Si une application SNMP est installée et que le service d’informations sur l’emplacement n’arrive pas à trouver une correspondance dans la base de données d’emplacements, service d’informations sur l’emplacement utilise l’adresse MAC fournie par le client pour interroger automatiquement l’application. Ensuite, à l’aide des informations de port et de commutateur renvoyées par l’application SNMP, le service d’informations sur l’emplacement interroge une fois de plus la base de données d’emplacements.

Pour plus d’informations, voir [Set-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsWebServiceConfiguration).

> [!NOTE]  
> Les adresses MAC ne sont pas disponibles sur les ordinateurs qui exécutent Windows 8.

## Pour configurer l’URL de l’application SNMP

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande suivante pour configurer l’URL de l’application SNMP.
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>"

