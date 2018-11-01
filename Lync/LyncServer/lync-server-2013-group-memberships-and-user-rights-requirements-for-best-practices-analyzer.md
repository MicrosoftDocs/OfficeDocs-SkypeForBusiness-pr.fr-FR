---
title: "Appart. à des gr. et conf. req. des droits d'ut. pour Best Practices Analyzer"
TOCtitle: "Appart. à des gr. et conf. req. des droits d'ut. pour Best Practices Analyzer"
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg591354(v=OCS.15)
ms:contentKeyID: 49299400
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Appartenances à des groupes et configuration requise des droits d’utilisateur pour Best Practices Analyzer

 

_**Dernière rubrique modifiée :** 2012-10-21_

Pour exécuter Best Practices Analyzer correctement, le compte d’utilisateur que vous utilisez pour vous connecter doit être membre du groupe Administrateurs sur l’ordinateur local. De plus, pour analyser votre environnement, le compte d’utilisateur doit être membre des groupes suivants :

  - **Admins du domaine**   Pour énumérer les informations des services de domaine Active Directory et appeler les fournisseurs WMI (Windows Management Instrumentation) sur les contrôleurs de domaines et les serveurs de catalogues globaux.

  - **Administrateurs**   Requis sur chaque ordinateur Lync Server 2013 interne et chaque serveur Edge pour appeler les fournisseurs WMI et accéder au registre.

  - **RTCUniversalReadOnlyAdmins**   Droits d’administration de Lync Server 2013 complets ou délégués en lecture seule.

  - **Administrateur Affichage seul d’Exchange**   Administrateur Affichage seul d’Exchange complet ou délégué sur l’organisation Microsoft Exchange.

Si votre compte d’utilisateur ne dispose pas des droits utilisateur suffisants, deux options s’offrent à vous :

  - À l’invite de commande, utilisez la commande **runas** pour exécuter l’outil sous un compte doté des droits utilisateur suffisants. La syntaxe est la suivante :
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - Sur la page **Connexion à Active Directory**, définissez les informations d’identification des comptes que vous prévoyez d’utiliser pour exécuter Best Practices Analyzer. Cliquez sur **Afficher les options de connexion avancées**. Vous pouvez entrer trois comptes : un pour vous connecter aux services de domaine Active Directory, un pour vous connecter aux serveurs EdgeLync Server 2013, et un pour vous connecter aux serveurs Exchange. Si vous ne spécifiez aucun de ces comptes, le compte utilisateur servant à la connexion et l’exécution de Best Practices Analyzer est utilisé.

