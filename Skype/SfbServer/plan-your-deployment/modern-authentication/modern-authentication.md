---
title: Planifier l’authentification moderne dans Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Rubriques de planification de l’authentification et de l’autorisation pour Skype Entreprise Server, y compris l’intégration avec d’autres produits
ms.openlocfilehash: c657a2b3609c5fb93f7f915c460cd3334f7fac03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816244"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Discussion sur l’authentification et l’autorisation dans Skype Entreprise

L’authentification et l’autorisation sont des concepts connexes, mais font un travail différent pour vous (bien que les deux soient nécessaires). En d’autres termes, l’authentisation (AuthN) dépend des secrets que seul un utilisateur valide connaît ou possède, et il peut s’agit d’un mot de passe, d’un code, d’une empreinte digitale, d’un certificat, d’une combinaison de revendications sur l’utilisateur qui sont vraies ou d’une combinaison de ces éléments utilisés ensemble. AuthN est un processus qui vous prouve que vous êtes ce que vous dites être.

L’autorisation (AuthZ) concerne ce à quoi vous avez accès une fois que vous avez démontré qui vous êtes. Il détermine ce que vous avez été autorisé à voir, modifier et accéder autrement. Par exemple, vous pouvez avoir un accès administrateur de collection de sites puissant à SharePoint Online, mais si vous basculez vers une autre charge de travail en ligne, comme Skype Entreprise Online, vous pouvez avoir les privilèges de résoudre les problèmes des utilisateurs, et non de modifier la configuration du ou des serveurs. Dans une troisième charge de travail, telle qu’Exchange Online, vous pouvez avoir uniquement l’accès de l’utilisateur moyen. AuthZ vérifie les informations et le nombre d’accès dont vous avez besoin pour les services/chargements, applications, fichiers et autres données.

Nos exemples impliquent des propriétés en ligne telles que SharePoint et Exchange Online, mais les processus d’AuthN et d’AuthZ fonctionnent en local et dans un local hybride de la même manière. En fin de compte, les outils tels qu’AAD Connect et ADFS sont impliqués dans l’article AuthN et AuthZ en synchronisant les comptes et mots de passe locaux dans AD du cloud (c’est-à-dire Azure AD), ou en s’instruisant dans le flux d’AuthZ afin qu’un utilisateur ne soit pas fréquemment invité à entrer ses informations d’identification, par exemple lorsque vous basculez entre les charges de travail dans le Cloud, créant des scénarios d'Sign-On unique. Toutefois, ils ne font pas, en eux-mêmes, partie intégrante des mécanismes.

Aujourd’hui, de nombreuses technologies considèrent ces processus (AuthN et AuthZ) comme un mécanisme unique, et vous entendez de nombreuses références au processus d’authentification qui incluent également l’autorisation. Il est important de se souvenir que la première étape de l’accès utilisateur est AuthN, qui prouve que vous êtes ce que vous dites être, et qu’AuthZ utilise la connaissance de l’utilisateur pour déterminer à quoi il a accès (comme vous le verrez avec Open Authorization ou OAuth).

  
## <a name="authentication-and-authorization-planning-topics"></a>Rubriques de planification de l’authentification et de l’autorisation

[Utilisation de l’authentification moderne (ADAL) avec Skype Entreprise](plan-adal.md)

[Topologies Skype Entreprise prises en charge avec l’authentification moderne](topologies-supported.md)

[Planification de la désactiver des méthodes d’authentification héritées en interne et en externe sur votre réseau.](turn-on-modern-auth.md)

