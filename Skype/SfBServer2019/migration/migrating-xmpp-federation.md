---
title: Migration de la fédération XMPP
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Les versions précédentes fournissaient une passerelle de protocole (XMPP) de messagerie et de présence extensible peut être déployée en tant qu’un rôle de serveur distinct pour autoriser la fédération avec des déploiements XMPP. La fonctionnalité XMPP n’est plus disponible et obsolètes dans Skype pour Business Server 2019. Si vous souhaitez poursuivre la fonctionnalité XMPP, qui peut être eu dans un environnement coexitence avec la version héritée (Skype pour Business Server 2015 / Lync Server 2013). La fonctionnalité XMPP est installée en deux parties : comme un XMPP proxy qui s’exécute sur hérité serveur Edge et la passerelle XMPP qui s’exécute sur le serveur frontal hérité.'
ms.openlocfilehash: c1c189d8d4b2e4fcd75b3d00d9789736f5bafc6a
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839537"
---
# <a name="migrating-xmpp-federation"></a>Migration de la fédération XMPP

Les versions précédentes fournissaient une passerelle de protocole (XMPP) de messagerie et de présence extensible peut être déployée en tant qu’un rôle de serveur distinct pour autoriser la fédération avec des déploiements XMPP. La fonctionnalité XMPP n’est plus disponible et est déconseillée dans Skype pour Business Server 2019. Si vous souhaitez poursuivre la fonctionnalité XMPP, vous pouvez le faire dans un environnement de coexistence avec une version héritée (Skype pour Business Server 2015 ou Lync Server 2013). La fonctionnalité XMPP est installée en deux parties : comme un XMPP proxy qui s’exécute sur hérité serveur Edge et la passerelle XMPP qui s’exécute sur le serveur frontal hérité. 
  
À partir du point de vue de la migration, les utilisateurs qui souhaitent bénéficier de la fonctionnalité XMPP doivent rester dans le serveur hérité et ne doivent pas être déplacés vers un Skype pour le pool d’entreprise Server 2019 mais continuent à utiliser la passerelle XMPP héritée. Cela est possible uniquement lorsque le partenaire fédéré XMPP est configuré dans Skype pour Business Server 2015 ou de Lync Server 2013. Vous ne devez pas migrer le serveur Edge hérité à Skype pour Business Server 2019 si vous souhaitez poursuivre la fonctionnalité XMPP. Toutefois, vous pouvez avoir coexistence entre le serveur Edge hérité (avec Proxy XMPP) et le Skype pour Business 2019 Edge Server.
  

    

