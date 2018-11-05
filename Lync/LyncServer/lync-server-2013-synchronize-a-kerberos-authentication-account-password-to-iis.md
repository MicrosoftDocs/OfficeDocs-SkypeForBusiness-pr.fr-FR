---
title: "LS 2013 : Synch. mdp de compte d’auth. Kerberos avec les serv. Internet (IIS)"
TOCTitle: Synchronisation d’un mot de passe de compte d’authentification Kerberos avec les services Internet (IIS)
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398107(v=OCS.15)
ms:contentKeyID: 49296126
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Synchronisation d’un mot de passe de compte d’authentification Kerberos avec les services Internet (IIS) dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2010-11-08_

Pour effectuer cette procédure vous devez avoir ouvert une session en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.

Dans un site, les serveurs frontaux, les serveurs Standard Edition et les directeurs peuvent utiliser un compte d’authentification Kerberos afin d’envoyer des demandes d’authentification au service services web. Cette procédure permet de rechercher chaque serveur exécutant services web dans un site auquel un compte Kerberos est affecté et de mettre à jour les paramètres de configuration des services Internet (IIS) pour utiliser le compte Kerberos. Pour plus d’informations, reportez-vous à [Définition d’un mot de passe de compte d’authentification Kerberos sur un serveur dans Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

## Pour définir et configurer un mot de passe de compte d’authentification Kerberos

1.  Ouvrez une session sur un ordinateur source (tel que fe01.contoso.com) en tant que membre du groupe RTCUniversalServerAdmins.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Depuis la ligne de commande Lync Server Management Shell, exécutez les deux commandes suivantes :
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    Exemple :
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    > [!IMPORTANT]  
    > Le nom de l’ordinateur source et celui de l’ordinateur de destination doivent être un nom de domaine complet du serveur. Vous ne pouvez pas utiliser le nom de domaine complet du pool sauf si le nom du pool est le même que celui de l’ordinateur que vous utilisez comme ordinateur source ou ordinateur de destination.    
    > [!IMPORTANT]  
    > Une fois que vous avez modifié l’authentification Kerberos, par exemple, si vous ajoutez ou supprimez un compte, vous devez exécuter <strong>Enable-CsTopology</strong> depuis l’invite de commandes Lync Server Management Shell.
