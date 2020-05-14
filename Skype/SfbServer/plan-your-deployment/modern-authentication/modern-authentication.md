---
title: Planifier l’authentification moderne dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Planification des rubriques relatives à l’authentification et à l’autorisation pour Skype entreprise Server, y compris l’intégration à d’autres produits
ms.openlocfilehash: 3b673a9f88895ac57277ef51b51fe0a4a27c64a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221578"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Présentation de l’authentification et de l’autorisation dans Skype entreprise

L’authentification et l’autorisation sont des concepts associés, mais un travail différent pour vous (bien que les deux sont nécessaires). En termes simples, authenciation (Authn) repose sur des secrets uniquement dont un utilisateur est informé ou avec, et qui peut être un mot de passe, du code, une empreinte, un certificat, une combinaison de revendications concernant l’utilisateur qui sont vraies ou une combinaison de ces éléments. Authn est un processus qui prouve que vous êtes la personne que vous prononcez.

Authorization (autorisation) concerne ce à quoi vous avez accès une fois que vous avez prouvé votre identité. Il détermine ce qui a été autorisé à afficher, modifier et accéder à d’autres. Par exemple, vous pouvez avoir un puissant accès administrateur de collection de sites à SharePoint Online, mais si vous basculez vers une autre charge de travail en ligne, comme Skype entreprise Online, vous pouvez avoir les privilèges pour résoudre les problèmes des utilisateurs, et ne pas modifier la configuration du serveur ou des serveurs. Dans une troisième charge de travail, telle qu’Exchange Online, vous pouvez uniquement avoir accès à l’utilisateur moyen. Authz vérifie quels sont les accès à vos services/worloads, vos applications, vos fichiers et d’autres données.

Nos exemples impliquent des propriétés en ligne telles que SharePoint et Exchange Online, mais les processus d’authentification et d’autorisation fonctionnent sur site et dans un environnement hybride de la même manière. En fin de compte, les outils comme AAD Connect et ADFS deviennent impliqués dans l’histoire Authn et authz en synchronisant les comptes locaux et les mots de passe dans l’annonce du Cloud (c’est-à-dire Azure AD), ou par une intrusion dans le flux des demandes d’autorisation afin qu’un utilisateur ne soit pas souvent invité à fournir des informations d’identification, disons quand il bascule entre les charges de travail Mais ils ne sont pas, en soi, habilités ou authnt, il ne s’agit que d’une partie de la mécanique.

À l’heure actuelle, de nombreuses technologies considèrent ces processus (Authn et authz) comme un mécanisme unique, et vous entendez de nombreuses références au processus d’authentification qui incluent également des autorisations dans ces derniers. Il est important de garder à l’esprit que la première étape de l’accès des utilisateurs est Authn, prouvant que vous êtes la personne que vous déclarez, et que la fonction auth utilise les connaissances de l’utilisateur pour déterminer ce à quoi il a accès (comme vous le verrez avec l’autorisation Open ou OAuth).

  
## <a name="authentication-and-authorization-planning-topics"></a>Rubriques relatives à l’authentification et à la planification des autorisations

[Utilisation de l’authentification moderne (ADAL) avec Skype entreprise](plan-adal.md)

[Topologies Skype entreprise prises en charge avec l’authentification moderne](topologies-supported.md)

[Planification de la désactivation interne et externe des méthodes d’authentification héritées sur votre réseau.](turn-on-modern-auth.md)

