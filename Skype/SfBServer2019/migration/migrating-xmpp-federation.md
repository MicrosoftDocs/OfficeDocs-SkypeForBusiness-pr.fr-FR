---
title: Migration de la fédération XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Les versions précédentes ont fourni une passerelle de service de messagerie et de présence extensible qui pouvait être déployée en tant que rôle de serveur distinct pour permettre la Fédération avec des déploiements de XMPP. La fonctionnalité XMPP n’est plus disponible & déconseillée dans Skype entreprise Server 2019. Si vous souhaitez continuer à utiliser la fonctionnalité XMPP, vous pouvez l’utiliser dans l’environnement coexitence avec la version héritée (Skype entreprise Server 2015/Lync Server 2013). La fonctionnalité XMPP est installée en deux parties: en tant que proxy XMPP qui s’exécute sur le serveur Edge hérité et sur la passerelle XMPP qui s’exécute sur le serveur frontal hérité.'
ms.openlocfilehash: fd2b51af84133e28e9a4de035333b1a282d71d38
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298189"
---
# <a name="migrating-xmpp-federation"></a>Migration de la fédération XMPP

Les versions précédentes ont fourni une passerelle de service de messagerie et de présence extensible qui pouvait être déployée en tant que rôle de serveur distinct pour permettre la Fédération avec des déploiements de XMPP. La fonctionnalité XMPP n’est plus disponible et est déconseillée dans Skype entreprise Server 2019. Si vous voulez continuer à utiliser la fonctionnalité XMPP, vous pouvez le faire dans un environnement de coexistence avec une version héritée (Skype entreprise Server 2015 ou Lync Server 2013). La fonctionnalité XMPP est installée en deux parties: en tant que proxy XMPP qui s’exécute sur le serveur Edge hérité et sur la passerelle XMPP qui s’exécute sur le serveur frontal hérité. 
  
Du point de vue de la migration, les utilisateurs qui souhaitent utiliser la fonctionnalité XMPP doivent demeurer sur le serveur hérité et ne doivent pas être déplacés vers un pool Skype entreprise Server 2019, mais continuer à utiliser l’ancienne passerelle XMPP. Ce n’est possible que lorsque le partenaire fédéré XMPP est configuré dans Skype entreprise Server 2015 ou Lync Server 2013. Pour continuer à utiliser la fonctionnalité XMPP, il est préférable de ne pas migrer le serveur Edge hérité vers Skype entreprise Server 2019. Toutefois, vous pouvez avoir coexistence du serveur Edge hérité (avec proxy XMPP) et du serveur Edge 2019 Skype entreprise.
  

    

