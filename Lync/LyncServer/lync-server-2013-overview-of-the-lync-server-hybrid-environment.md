---
title: 'Lync Server 2013 : Vue d’ensemble de l’environnement hybride Lync Server'
TOCTitle: Vue d’ensemble de l’environnement hybride Lync Server 2013
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204669(v=OCS.15)
ms:contentKeyID: 49296240
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble de l’environnement hybride Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

L’environnement hybride Lync Server 2013 fait référence à un déploiement dans lequel certains utilisateurs sont hébergés sur Lync Server 2013 en local tandis que d’autres sont hébergés sur Lync Online, mais ils partagent tous le même domaine, tel que user@contoso.com.

## À propos de ce guide

Ce guide décrit les tâches permettant de configurer votre environnement Lync Server 2013 afin qu’il soit interopérable avec Lync Online, puis de déplacer les utilisateurs depuis votre déploiement local afin qu’ils puissent se servir de Lync Online.

## Conditions requises

Vous devez disposer des applications et utilitaires ci-après pour configurer un déploiement dans le cadre d’un environnement hybride. Les programmes d’installation de ces fichiers se trouvent sur le support d’installation fourni pour votre déploiement, ainsi qu’aux liens indiqués dans la liste suivante.

  - [Active Directory Federation Services (AD FS) 2.0](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Outil de synchronisation d’annuaire Microsoft 9.1](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [Installation de Windows PowerShell avec l’authentification unique pour AD FS](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - L’Assistant de connexion Microsoft Online Services (msoidcli-7.0.msi) est inclus dans la configuration du Bureau pour Office 365, que vous pouvez obtenir à partir de la page de téléchargement accessible sur le portail d’administration d’Office 365.

## Informations d’identification de l’administrateur

Lorsque le système vous invite à indiquer vos informations d’identification d’administrateur, utilisez le nom d’utilisateur et le mot de passe obtenus pour le compte d’administrateur du client Office 365. Vous utiliserez également ces informations d’identification pour configurer Active Directory Federation Services (AD FS) 2.0, la synchronisation d’annuaire, l’authentification unique, la fédération et le déplacement des utilisateurs vers Lync Online.

## Connexion à Lync Online PowerShell

Les administrateurs peuvent désormais utiliser Windows PowerShell pour gérer Lync Online et leurs comptes d’utilisateur Lync Online. Pour ce faire, vous devez commencer par télécharger et installer le module Connecteur Lync Online via le Centre de téléchargement Microsoft (http://go.microsoft.com/fwlink/?LinkId=294688). Pour plus d’informations sur le téléchargement, l’installation et l’utilisation du module Connecteur Lync Online et des informations détaillées sur l’utilisation de Windows PowerShell pour gérer Lync Online, reportez-vous à [Utilisation de Windows PowerShell pour gérer Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

