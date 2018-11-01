---
title: 'Lync Server 2013 : Création d’un compte d’authentification Kerberos'
TOCTitle: Création d’un compte d’authentification Kerberos
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398449(v=OCS.15)
ms:contentKeyID: 49297416
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création d’un compte d’authentification Kerberos dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-01-02_

Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine au minimum en tant que membre du groupe Admins du domaine.

Vous pouvez créer des comptes d’authentification Kerberos pour chaque site, ou vous pouvez créer un seul compte d’authentification Kerberos et l’utiliser pour tous les sites. Utilisez les applets de commande Windows PowerShell pour créer et gérer les comptes, notamment l’identification des comptes affectés à chaque site. Le Générateur de topologie et le Panneau de configuration Lync Server 2013 n’affichent pas les comptes d’authentification Kerberos. Suivez la procédure ci-après pour créer un ou plusieurs comptes d’utilisateur pour l’authentification Kerberos.

## Pour créer un compte Kerberos

1.  En tant que membre du groupe Admins du domaine, ouvrez une session sur un ordinateur du domaine exécutant Lync Server 2013 ou sur un ordinateur où les outils d’administration ont été installés.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Depuis la ligne de commande, exécutez la commande suivante :
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    Exemple :
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  Vérifiez que l’objet Ordinateur a été créé en ouvrant Utilisateurs et ordinateurs Active Directory, développez le conteneur **Utilisateurs** , puis vérifiez que l’objet Ordinateur du compte d’utilisateur se trouve dans le conteneur.

