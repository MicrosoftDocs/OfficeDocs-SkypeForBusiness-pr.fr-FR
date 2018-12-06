---
title: 'Lync Server 2013 : Suppression de l’authentification Kerberos d’un site'
TOCTitle: Suppression de l’authentification Kerberos d’un site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398749(v=OCS.15)
ms:contentKeyID: 49298093
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression de l’authentification Kerberos d’un site dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-01-16_

Pour effectuer cette procédure vous devez avoir ouvert une session en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.

Si vous devez supprimer l’authentification Kerberos d’un site ou supprimer un site, vous devez supprimer l’affectation du compte d’authentification Kerberos du site à l’aide de l’applet de commande **Remove-CsKerberosAccountAssignment**. Utilisez la procédure suivante pour supprimer l’affectation du compte d’authentification Kerberos, ce qui a pour effet de supprimer l’affectation de tous les ordinateurs présents sur le site.

> [!WARNING]  
> Si vous supprimez définitivement le compte activé pour Kerberos, vous devriez utiliser le composant Utilisateurs et ordinateurs Active Directory pour le supprimer des services de domaine Active Directory après avoir supprimé l’affectation. Si vous envisagez d’utiliser l’objet ultérieurement, vous pouvez peut-être conserver l’objet Active Directory.

## Pour supprimer l’authentification Kerberos d’un site

1.  En tant que membre du groupe RTCUniversalServerAdmins, ouvrez une session sur un ordinateur du domaine qui exécute Lync Server 2013 ou sur un ordinateur où les outils d’administration sont installés.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Depuis la ligne de commande, exécutez les deux commandes suivantes :
    
    ```
    Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
    ```
    ```
    Enable-CsTopology
    ```
    Exemple :
    
    ```
    Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
    ```
    ```
    Enable-CsTopology
    ```
    
    > [!IMPORTANT]  
    > Une fois que vous avez modifié l’authentification Kerberos, par exemple, si vous ajoutez ou supprimez un compte, vous devez exécuter <strong>Enable-CsTopology</strong> depuis l’invite de commandes Lync Server Management Shell.
