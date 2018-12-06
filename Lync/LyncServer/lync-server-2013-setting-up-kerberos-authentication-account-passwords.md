---
title: "Lync Server 2013 : Conf. des mots de passe de compte d’auth. Kerberos"
TOCTitle: Configuration des mots de passe de compte d’authentification Kerberos
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412870(v=OCS.15)
ms:contentKeyID: 49298597
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des mots de passe de compte d’authentification Kerberos dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2010-11-03_

Après avoir créé l’objet ordinateur pour le compte d’authentification Kerberos, vous pouvez configurer le mot de passe pour le compte. Vous exécutez l’applet de commande Windows PowerShell pour définir le mot de passe du compte Kerberos sur un serveur. Vous pouvez définir le mot de passe sur l’objet créé pour l’authentification Kerberos. Le mot de passe peut être défini sur une valeur connue, mais par défaut il s’agit d’un mot de passe aléatoire. Il est valable pour toutes les sources d’authentification Kerberos qui utilisent le compte. Vous utilisez les applets de commande Windows PowerShell pour configurer et gérer les mots de passe de compte Kerberos.

> [!NOTE]  
> L’objet de compte Kerberos est un objet ordinateur qui utilise le paramètre UserAccount pour les opérations dans les applets de commande Windows PowerShell référencées. Notez qu’il ne s’agit pas d’une erreur, mais du comportement prévu de l’applet de commande lorsqu’elle est utilisée pour la création et la maintenance du compte Kerberos.

## Dans cette section

  - [Définition d’un mot de passe de compte d’authentification Kerberos sur un serveur dans Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [Synchronisation d’un mot de passe de compte d’authentification Kerberos avec les services Internet (IIS) dans Lync Server 2013](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

