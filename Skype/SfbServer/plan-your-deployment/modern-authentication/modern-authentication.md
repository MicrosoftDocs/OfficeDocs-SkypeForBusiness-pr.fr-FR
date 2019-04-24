---
title: Planifier l'authentification moderne dans Skype Entreprise
ms.reviewer: ''
ms.author: tracyp
author: MSFTTracyP
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Rubriques de planification pour l’authentification et d’autorisation pour Skype pour Business Server, y compris l’intégration avec d’autres produits
ms.openlocfilehash: 662eb90758bb22a9ef65492d9c9c1a99af778f23
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214116"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Discuter d’authentification et autorisation dans Skype pour les entreprises

Authentification et autorisation sont des concepts liés, mais faire travail différente (même si les deux sont nécessaires). Mettre en termes simples, authenciation (authentification) dépend des clés secrètes uniquement un utilisateur valid sait ou a, et qui peut être un mot de passe, code, empreinte, certificat, une combinaison de revendications relatives à l’utilisateur qui sont remplies ou une combinaison de ces facteurs utilisés conjointement. Authentification est un processus en prouver que vous êtes qui vous dites que vous êtes.

Autorisation (AuthZ) concerne ce que vous avez accès à une fois que vous avez prouvé qui vous êtes. Il détermine ce que vous avez été autorisé à voir, modifier et dans le cas contraire. Par exemple, avoir puissants accès administrateur de Collection de sites vers SharePoint Online, mais si vous passez à une autre charge de travail en ligne, comme Skype pour Business Online, peut avoir les privilèges pour résoudre les problèmes de l’utilisateur, pas modifier la configuration de la ou les serveurs. Dans une charge de travail tiers, tels que Exchange Online, peut-être uniquement accès au moyen de l’utilisateur. AuthZ vérifie les et dans quelle proportion accès à des services/worloads, des applications, fichiers et autres données.

Nos exemples impliquent online propriétés telles que SharePoint et Exchange online, mais les processus d’authentification et AuthZ fonctionnent sur site et dans un environnement local hybride la même manière. En définitive, les outils tels que DAS se connecter et ADFS impliqués dans l’article et d’authentification et AuthZ par synchronisation comptes locaux et mots de passe dans le nuage de l’annonce (c'est-à-dire Azure AD dans le cas d’Office 365 ou Azure), ou y converser dans le flux de AuthZ ainsi que un utilisateur n’est pas fréquemment invité à entrer leurs informations d’identification, par exemple lorsque vous basculez entre les charges de travail dans le nuage, création de scénarios Single Sign-On. Mais ils ne sont pas, en soi, seul responsable ou AuthZ, une partie seulement des mécanismes.

Aujourd'hui, les technologies de prendre en compte ces processus (et d’authentification et AuthZ) à un mécanisme, et vous entendez de références à des processus d’authentification qui incluent également l’autorisation dans les. Il est important de noter que la première étape de l’accès des utilisateurs est le seul, prouver que vous êtes qui vous dites que vous avez, et que AuthZ utilise la base de connaissances qui est l’utilisateur pour déterminer quel qu’il a accès aux (comme vous verrez avec Open Authorization ou OAuth).

  
## <a name="authentication-and-authorization-planning-topics"></a>Rubriques de l’authentification et autorisation de planification

[How to use Modern Authentication (ADAL) with Skype for Business](plan-adal.md)

[Skype for Business topologies supported with Modern Authentication](topologies-supported.md)

[Envisagez de désactiver les méthodes d’authentification Legacy internes et externes à votre réseau.](turn-on-modern-auth.md)

