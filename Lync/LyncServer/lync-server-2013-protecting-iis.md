---
title: 'Lync Server 2013 : protection des services Internet (IIS)'
TOCTitle: Protection des services Internet (IIS) dans Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn518332(v=OCS.15)
ms:contentKeyID: 60484504
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Protection des services Internet (IIS) dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-12-05_

Dans Microsoft Office Communications Server 2007 et Microsoft Office Communications Server 2007 R2, les services Internet (IIS) étaient exécutés dans un compte d’utilisateur standard, ce qui créait potentiellement des problèmes : si ce mot de passe était arrivé à expiration, vous pouviez perdre vos services web, un problème souvent difficile à diagnostiquer. Pour éviter le problème d’expiration des mots de passe, Microsoft Lync Server 2013 permet de créer un compte d’ordinateur (pour un ordinateur qui n’existe pas réellement) qui peut servir de principal d’authentification pour tous les ordinateurs d’un site qui exécute des services Internet (IIS). Comme ces comptes utilisent le protocole d’authentification Kerberos, les comptes sont appelés « comptes Kerberos », tandis que la nouvelle procédure d’authentification est appelée « authentification web Kerberos ». Cela permet de gérer tous vos serveurs de service Internet (IIS) en utilisant un seul compte.

Pour exécuter vos serveurs avec ce principal d’authentification, vous devez d’abord créer un compte d’ordinateur en utilisant l’applet de commande New-CsKerberosAccount. Ce compte est ensuite affecté à un ou plusieurs sites. Une fois l’affectation effectuée, l’association entre le compte et le site Lync Server 2013 est activée en exécutant l’applet de commande Enable-CsTopology. Cela crée, entre autres, le nom du principal de service (SPN) requis dans les services de domaine Active Directory. Les noms SPN permettent aux applications clientes de localiser un service. Pour plus d’informations, reportez-vous à la section [New-CsKerberosAccount](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsKerberosAccount) du manuel d’utilisation.

## Meilleures pratiques

Pour permettre d’augmenter la sécurité des services Internet (IIS), il est recommandé de mettre en oeuvre un compte Kerberos pour les services Internet (IIS). Si vous ne mettez pas en oeuvre de compte Kerberos, les services Internet (IIS) sont exécutés avec un compte d’utilisateur standard.

