---
title: "Lync Server 2013 : Attribution d’un compte d’auth. Kerberos sur un site"
TOCTitle: Attribution d’un compte d’authentification Kerberos sur un site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425901(v=OCS.15)
ms:contentKeyID: 49296971
ms.date: 04/19/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Attribution d’un compte d’authentification Kerberos sur un site dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2017-04-18_

Pour effectuer cette procédure vous devez avoir ouvert une session en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.

Après avoir créé le compte Kerberos, vous devez l’affecter à un site. Il s’agit d’un site Lync Server 2013 et non d’un site Active Directory. Vous pouvez créer plusieurs comptes d’authentification Kerberos par déploiement, mais vous ne pouvez affecter qu’un seul compte à un site. Pour affecter un compte d’authentification Kerberos existant à un site, procédez comme suit. Pour plus d’informations sur la façon de créer le compte Kerberos, reportez-vous à [Création d’un compte d’authentification Kerberos dans Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).

## Pour affecte un compte d’authentification Kerberos à un site

1.  En tant que membre du groupe RTCUniversalServerAdmins, ouvrez une session sur un ordinateur du domaine qui exécute Lync Server 2013 ou sur un ordinateur où les outils d’administration sont installés.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Depuis la ligne de commande, exécutez les deux commandes suivantes :
    
    ```
    New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount" -Identity "site:SiteName"
    ```
    ```
    Enable-CsTopology
    ```
    Exemple :
    
    ```
    New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth" -Identity "site:redmond"
    ```
    ```
    Enable-CsTopology
    ```
    
    > [!NOTE]  
    > Vous devez spécifier le paramètre Compte d’utilisateur au format Domaine\Utilisateur. Le format Utilisateur@Domaine.extension n’est pas pris en charge pour la référence aux objets créés à des fins d’authentification Kerberos.    
    > [!IMPORTANT]  
    > Une fois que vous avez modifié l’authentification Kerberos, par exemple, si vous ajoutez ou supprimez un compte, vous devez exécuter <strong>Enable-CsTopology</strong> depuis l’invite de commandes Lync Server Management Shell.
