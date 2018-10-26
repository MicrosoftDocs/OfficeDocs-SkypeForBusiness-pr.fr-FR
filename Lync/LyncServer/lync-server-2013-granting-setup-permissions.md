﻿---
title: 'Lync Server 2013 : Octroi d’autorisations de configuration'
TOCTitle: Octroi d’autorisations de configuration
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398225(v=OCS.15)
ms:contentKeyID: 49296354
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Octroi d’autorisations de configuration dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-08-27_

L’applet de commande **Grant-CsSetupPermission** vous permet d’ajouter des autorisations Read, Write, ReadSPN et WriteSPN au groupe RTCUniversalServerAdmins d’une unité d’organisation (UO) Active Directory spécifiée. Les membres du groupe RTCUniversalServerAdmins dans cette unité d’organisation peuvent alors installer des serveurs exécutant Lync Server 2013 dans le domaine spécifié sans faire partie du groupe Administrateurs du domaine.

L’applet de commande **Test-CsSetupPermission** vous permet de vérifier les autorisations que vous avez configurées à l’aide de l’applet de commande **Grant-CsSetupPermission**.

L’applet de commande **Revoke-CsSetupPermission** vous permet de supprimer les autorisations que vous avez accordées à l’aide de l’applet de commande **Grant-CsSetupPermission**.

## Pour accorder des autorisations de configuration

1.  Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez accorder des autorisations de configuration. Utilisez un compte membre du groupe Administrateurs du domaine ou du groupe Administrateurs d’entreprise si l’unité d’organisation (UO) est dans un autre domaine enfant.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Vous pouvez spécifier le paramètre ComputerOu selon le contexte d’appellation par défaut du domaine spécifié (par exemple, CN=ordinateurs). Vous pouvez également spécifier ce paramètre comme nom unique complet (DN) de l’unité d’organisation (par exemple, « CN=ordinateurs,DC=Contoso,DC=com »). Dans le dernier cas, vous devez spécifier un DN d’unité d’organisation (UO) qui correspond au domaine que vous spécifiez.
    
    Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.

## Pour vérifier les autorisations de configuration

1.  Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez vérifier les autorisations de configuration que vous avez accordées à l’aide de l’applet de commande **Grant-CsSetupPermission**. Utilisez un compte membre du groupe Administrateurs du domaine ou du groupe Administrateurs d’entreprise si l’unité d’organisation (UO) est dans un autre domaine enfant.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    Vous pouvez spécifier le paramètre ComputerOu selon le contexte d’appellation par défaut du domaine spécifié (par exemple, CN=ordinateurs). Vous pouvez également spécifier ce paramètre comme nom unique complet (DN) de l’unité d’organisation (par exemple, « CN=ordinateurs,DC=Contoso,DC=com »). Dans le dernier cas, vous devez spécifier un DN d’unité d’organisation (UO) qui correspond au domaine que vous spécifiez.
    
    Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.

## Pour révoquer des autorisations de configuration

1.  Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez révoquer les autorisations de configuration que vous avez accordées à l’aide de l’applet de commande **Grant-CsSetupPermission**. Utilisez un compte membre du groupe Administrateurs du domaine ou du groupe Administrateurs d’entreprise si l’unité d’organisation (UO) est dans un autre domaine enfant.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Vous pouvez spécifier le paramètre ComputerOu selon le contexte d’appellation par défaut du domaine spécifié (par exemple, CN=ordinateurs). Vous pouvez également spécifier ce paramètre comme nom unique complet (DN) de l’unité d’organisation (par exemple, « CN=ordinateurs,DC=Contoso,DC=com »). Dans le dernier cas, vous devez spécifier un DN d’unité d’organisation (UO) qui correspond au domaine que vous spécifiez.
    
    Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.

