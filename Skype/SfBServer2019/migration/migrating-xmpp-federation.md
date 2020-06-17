---
title: Migration de la fédération XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Les versions précédentes fournissaient une passerelle XMPP (extensible Messaging and Presence Protocol) qui pourrait être déployée en tant que rôle serveur distinct afin d’autoriser la Fédération avec des déploiements XMPP. La fonctionnalité XMPP n’est plus disponible & déconseillée dans Skype entreprise Server 2019. Si vous souhaitez continuer à utiliser la fonctionnalité XMPP, vous pouvez l’utiliser dans un environnement coexitence avec une version héritée (Skype entreprise Server 2015/Lync Server 2013). La fonctionnalité XMPP est installée en deux parties : en tant que proxy XMPP qui s’exécute sur le serveur Edge hérité et la passerelle XMPP qui s’exécute sur le serveur frontal hérité.'
ms.openlocfilehash: 71b6c213450f51ea4b3fe1f351e22dbb992ce8ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752646"
---
# <a name="migrating-xmpp-federation"></a>Migration de la fédération XMPP

Les versions précédentes fournissaient une passerelle XMPP (extensible Messaging and Presence Protocol) qui pourrait être déployée en tant que rôle serveur distinct afin d’autoriser la Fédération avec des déploiements XMPP. La fonctionnalité XMPP n’est plus disponible et est déconseillée dans Skype entreprise Server 2019. Si vous souhaitez continuer à utiliser la fonctionnalité XMPP, vous pouvez le faire dans un environnement de coexistence avec une version héritée (Skype entreprise Server 2015 ou Lync Server 2013). La fonctionnalité XMPP est installée en deux parties : en tant que proxy XMPP qui s’exécute sur le serveur Edge hérité et la passerelle XMPP qui s’exécute sur le serveur frontal hérité. 
  
Du point de vue de la migration, les utilisateurs qui souhaitent utiliser la fonctionnalité XMPP doivent rester sur le serveur hérité et ne doivent pas être déplacés vers un pool Skype entreprise Server 2019, mais continuer à utiliser la passerelle XMPP héritée. Ceci n’est possible que lorsque le partenaire fédéré XMPP est configuré dans Skype entreprise Server 2015 ou Lync Server 2013. Vous ne devez pas migrer le serveur Edge hérité vers Skype entreprise Server 2019 si vous souhaitez continuer à utiliser la fonctionnalité XMPP. Toutefois, vous pouvez coexister le serveur Edge hérité (avec le proxy XMPP) et le serveur Edge Skype entreprise 2019.
  

    

