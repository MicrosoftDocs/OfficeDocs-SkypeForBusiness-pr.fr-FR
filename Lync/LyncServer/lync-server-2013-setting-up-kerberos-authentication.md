---
title: 'Lync Server 2013 : Configuration de l’authentification Kerberos'
TOCTitle: Configuration de l’authentification Kerberos
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398976(v=OCS.15)
ms:contentKeyID: 49299080
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de l’authentification Kerberos dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

Lync Server 2013 prend en charge l’authentification NTLM et Kerberos pour les services web. Office Communications Server 2007 et Office Communications Server 2007 R2 utilisaient les comptes d’utilisateur par défaut RTCComponentService et RTCService pour exécuter les pools d’applications des services web afin d’attribuer un nom principal de service (SPN) aux comptes d’utilisateur et de jouer le rôle de principal d’authentification. Lync Server utilise NetworkService pour exécuter les services web. Les noms principaux de service ne peuvent pas être attribués à NetworkService.

Pour résoudre ce problème; à savoir ne pas disposer d’objets Active Directory pour gérer les SPN, Panneau de configuration Lync Server peut utiliser des objets de compte d’ordinateur à cet effet. Ces objets peuvent contenir les SPN et leurs mots de passe n’expirent pas, ce qui n’était pas le cas avec les comptes utilisateur des versions précédentes.

Utilisez les applets de commande Windows PowerShell pour configurer les objets d’ordinateur afin de permettre l’authentification Kerberos.

## Dans cette section

  - [Conditions prérequises à l’activation de l’authentification Kerberos dans Lync Server 2013](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [Création d’un compte d’authentification Kerberos dans Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [Attribution d’un compte d’authentification Kerberos sur un site dans Lync Server 2013](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [Configuration des mots de passe de compte d’authentification Kerberos dans Lync Server 2013](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [Ajout d’une authentification Kerberos à d’autres sites dans Lync Server 2013](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [Suppression de l’authentification Kerberos d’un site dans Lync Server 2013](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [Test et création de rapports sur l’état et l’affectation de l’authentification Kerberos dans Lync Server 2013](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

