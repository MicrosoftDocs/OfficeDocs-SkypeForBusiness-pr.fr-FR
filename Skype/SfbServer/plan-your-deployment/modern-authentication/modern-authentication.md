---
title: Planifier l'authentification moderne dans Skype Entreprise
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
description: Rubriques de planification pour l’authentification et l’autorisation de Skype entreprise Server, y compris l’intégration avec d’autres produits
ms.openlocfilehash: f732e4afa6b82554c4248a244276e5e5b60c71cc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815842"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Aborder l’authentification et l’autorisation dans Skype entreprise

L’authentification et l’autorisation sont des concepts associés, mais le fonctionnement est différent pour vous (les deux sont nécessaires). Placées en termes simples, authenciation (Authn) dépend de secrets uniquement qu’un utilisateur valide connaît ou a et qu’il peut s’agir d’un mot de passe, d’un code, d’une empreinte, d’un certificat, d’une combinaison de plaintes sur l’utilisateur qui sont vraies ou d’une combinaison de ces éléments utilisés ensemble. Authn est un processus qui prouve que vous êtes le nom de votre interlocuteur.

Les autorisations (auth) concernent les personnes auxquelles vous avez accès lorsque vous avez prouvé votre identité. Elle détermine ce que vous êtes autorisé à consulter, modifier et autrement accès. Par exemple, vous pouvez avoir accès à un administrateur de collection de sites puissant pour accéder à SharePoint Online, mais si vous basculez vers une autre charge de travail en ligne (par exemple, Skype entreprise Online), il est possible que vous disposiez des privilèges appropriés pour résoudre les problèmes des utilisateurs et ne pas modifier la configuration du serveur ou serveurs. Dans un troisième travail de charge de travail, tel qu’Exchange Online, vous ne disposez pas de l’accès moyen pour l’utilisateur. Authz vérifie le niveau d’accès dont vous avez besoin aux services/worloads, aux applications, aux fichiers et aux autres données.

Nos exemples impliquent des propriétés en ligne telles que SharePoint et Exchange Online, mais les processus de Authn et de auth-site travaillent localement et dans un environnement hybride de la même manière. Pour finir, les outils tels que AAD Connect et les services ADFS sont impliqués dans l’histoire d’Authn et de authz en synchronisant des comptes et des mots de passe locaux dans la publicité du Cloud (qui est Azure AD dans le cas d’Office 365 ou Azure), ou par une intrusion dans le flux d’autorisation de sorte que un utilisateur n’est pas fréquemment invité à entrer ses informations d’identification, par exemple lorsque vous basculez entre les charges de travail dans le Cloud et créez des scénarios d’authentification unique. Toutefois, elles ne sont pas, en soi, d’auth ou d’auth responsable, qu’il s’agit d’une seule et même partie de la mécanique.

Aujourd’hui, bon nombre de technologies envisagent ces processus (Authn et authz) comme un mécanisme unique et vous entendez de nombreuses références au processus d’authentification qui incluent également une autorisation. Il est important de garder à l’esprit que la première étape de l’accès utilisateur est Authn, en vous prouvant qu’il s’agit de votre identité et qu’elle utilise les connaissances de la personne à laquelle l’utilisateur a accès (comme le montre avec l’autorisation Open ou OAuth).

  
## <a name="authentication-and-authorization-planning-topics"></a>Rubriques relatives à l’authentification et à la planification de l’autorisation

[How to use Modern Authentication (ADAL) with Skype for Business](plan-adal.md)

[Skype for Business topologies supported with Modern Authentication](topologies-supported.md)

[Planification de la désactivation de méthodes d’authentification héritées internes et externes à votre réseau.](turn-on-modern-auth.md)

