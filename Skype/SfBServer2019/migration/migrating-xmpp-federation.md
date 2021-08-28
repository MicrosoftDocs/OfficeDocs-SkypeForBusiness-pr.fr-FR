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
ms.localizationpriority: medium
description: 'Les versions précédentes fournissaient une passerelle XMPP (Extensible Messaging and Presence Protocol) qui pouvait être déployée en tant que rôle serveur distinct pour permettre la fédération avec les déploiements XMPP. La fonctionnalité XMPP n’est plus disponible & est désormais Skype Entreprise Server 2019. Si vous souhaitez continuer avec la fonctionnalité XMPP, celle-ci peut être disponible dans un environnement de coexitence avec la version héritée (Skype Entreprise Server 2015/ Lync Server 2013). La fonctionnalité XMPP est installée en deux parties : en tant que proxy XMPP qui s’exécute sur le serveur Edge hérité et en tant que passerelle XMPP qui s’exécute sur le serveur frontal hérité.'
ms.openlocfilehash: a0c3eeaa6218c6e3b3726f755adcca6083a9ac3f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580128"
---
# <a name="migrating-xmpp-federation"></a>Migration de la fédération XMPP

Les versions précédentes fournissaient une passerelle XMPP (Extensible Messaging and Presence Protocol) qui pouvait être déployée en tant que rôle serveur distinct pour permettre la fédération avec les déploiements XMPP. La fonctionnalité XMPP n’est plus disponible et est Skype Entreprise Server 2019. Si vous souhaitez continuer avec la fonctionnalité XMPP, vous pouvez le faire dans un environnement de coexistence avec une version héritée (Skype Entreprise Server 2015 ou Lync Server 2013). La fonctionnalité XMPP est installée en deux parties : en tant que proxy XMPP qui s’exécute sur le serveur Edge hérité et en tant que passerelle XMPP qui s’exécute sur le serveur frontal hérité. 
  
Du point de vue de la migration, les utilisateurs qui souhaitent bénéficier de la fonctionnalité XMPP doivent rester sur le serveur hérité et ne doivent pas être déplacés vers un pool Skype Entreprise Server 2019, mais continuer à utiliser la passerelle XMPP héritée. Cela est possible uniquement lorsque le partenaire fédéré XMPP est configuré dans Skype Entreprise Server 2015 ou Lync Server 2013. Vous ne devez pas migrer le serveur Edge hérité vers Skype Entreprise Server 2019 si vous souhaitez continuer avec la fonctionnalité XMPP. Toutefois, vous pouvez avoir une coexistence entre le serveur Edge hérité (avec le proxy XMPP) et le serveur Edge Skype Entreprise 2019.
  

    

