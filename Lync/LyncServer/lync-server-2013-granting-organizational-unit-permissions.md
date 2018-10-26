---
title: 'Lync Server 2013 : Octroi d’autorisations d’unité organisationnelle'
TOCTitle: Octroi d’autorisations d’unité organisationnelle
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398763(v=OCS.15)
ms:contentKeyID: 49298141
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Octroi d’autorisations d’unité organisationnelle dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-05-14_

Vous pouvez utiliser l’applet de commande **Grant-CsOuPermission** pour accorder des autorisations à des objets dans des unités d’organisation spécifiées afin que les membres des groupes universels RTC créés lors de la préparation de la forêt puissent accéder à ces objets sans être membres du groupe Administrateurs du domaine. Les autorisations ajoutées à l’unité d’organisation spécifiée sont identiques à celles que l’applet de commande **Enable-CsAdDomain** ajoute aux conteneurs d’ordinateurs et d’utilisateurs au cours de la préparation du domaine.

L’applet de commande **Test-CsOuPermission** vous permet de vérifier les autorisations que vous avez configurées à l’aide de l’applet de commande **Grant-CsOuPermission**.

L’applet de commande **Revoke-CsOuPermission** vous permet de supprimer les autorisations que vous avez accordées à l’aide de l’applet de commande **Grant-CsOuPermission**.

## Pour accorder des autorisations d’unité d’organisation

1.  Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez accorder des autorisations d’unité d’organisation. Utilisez un compte membre du groupe Administrateurs du domaine ou Administrateurs d’entreprise si l’unité d’organisation est dans un autre domaine enfant.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.

## Pour vérifier les autorisations d’unité d’organisation

1.  Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez vérifier les autorisations d’unité d’organisation que vous avez accordées à l’aide de l’applet de commande **Grant-CsOuPermission**. Utilisez un compte membre du groupe Administrateurs du domaine ou Administrateurs d’entreprise si l’unité d’organisation est dans un autre domaine enfant.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.

## Pour révoquer les autorisations d’unité d’organisation

1.  Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez révoquer les autorisations d’unité d’organisation que vous avez accordées à l’aide de l’applet de commande **Grant-CsOuPermission**. Utilisez un compte membre du groupe Administrateurs du domaine ou Administrateurs d’entreprise si l’unité d’organisation est dans un autre domaine enfant.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.

