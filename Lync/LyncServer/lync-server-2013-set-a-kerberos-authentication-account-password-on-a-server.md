---
title: "Lync Server 2013 : Déf. d’un mdp de compte d’auth. Kerberos sur un serveur"
TOCTitle: Définition d’un mot de passe de compte d’authentification Kerberos sur un serveur
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398734(v=OCS.15)
ms:contentKeyID: 49298061
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition d’un mot de passe de compte d’authentification Kerberos sur un serveur dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-01-16_

Pour effectuer cette procédure vous devez avoir ouvert une session en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.

Vous devez configurer un mot de passe sur le compte Kerberos pour chaque site disposant de serveurs frontaux, de serveurs Standard Edition et de directeurs. Vous pouvez configurer le mot de passe en exécutant l’applet de commande Windows PowerShell**Set-CsKerberosAccountPassword** sur un serveur du site (par exemple, un serveur frontal). Vous devez exécuter l’applet de commande **Set-CsKerberosAccountPassword** pour chaque site. L’applet de commande configure les services Internet (IIS) pour les services web, puis définit le mot de passe sur le compte de l’ordinateur dans services de domaine Active Directory. Une autre méthode, basée sur le type de paramètre utilisé dans l’applet de commande, configure les services Internet (IIS) sur un serveur tout en utilisant un autre serveur ayant été configuré comme source du mot de passe du compte Kerberos.

Lorsque vous utilisez l’applet de commande **Set-CsKerberosAccountPassword** pour définir un mot de passe, Kerberos définit le mot de passe en tant que chaîne générée de manière aléatoire. Cette applet de commande contacte toutes les instances des services Internet (IIS) de tous les sites centraux Lync Server 2013 auxquels ce compte est affecté.

## Pour définir un mot de passe de compte d’authentification Kerberos

1.  Ouvrez une session sur un ordinateur du domaine sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Depuis la ligne de commande, exécutez les deux commandes suivantes :
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    Exemple :
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    > [!NOTE]  
    > Vous devez spécifier le paramètre Compte d’utilisateur au format Domaine\Utilisateur. Le format Utilisateur@Domaine.extension n’est pas pris en charge pour le référencement des objets Ordinateur créés à des fins d’authentification Kerberos.    
    > [!IMPORTANT]  
    > Une fois que vous avez modifié l’authentification Kerberos, par exemple, si vous ajoutez ou supprimez un compte, vous devez exécuter <strong>Enable-CsTopology</strong> depuis l’invite de commandes Lync Server Management Shell.
