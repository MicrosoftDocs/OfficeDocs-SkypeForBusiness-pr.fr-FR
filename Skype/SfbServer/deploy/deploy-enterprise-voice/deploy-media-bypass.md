---
title: Déployer le contournement de média dans Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
description: Déployer le contournement de média dans Skype pour Business Server Enterprise Voice. Cela Inclut les conditions préalables et la liste de vérification de la procédure de déploiement.
ms.openlocfilehash: 307c3ff66adf042a984c544a722517d2709154d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223105"
---
# <a name="deploy-media-bypass-in-skype-for-business-server"></a>Déployer le contournement de média dans Skype pour Business Server
 
Déployer le contournement de média dans Skype pour Business Server Enterprise Voice. Cela Inclut les conditions préalables et la liste de vérification de la procédure de déploiement.
  
Cette rubrique suppose que vous avez déjà publié et configuré au moins un ou plusieurs serveurs de médiation et entre homologues au moins une passerelle pour fournir une connectivité PSTN. Pour plus d’informations sur ces tâches, voir [déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server](deploy-a-mediation-server.md) et [définir une passerelle dans le Générateur de topologie dans Skype pour Business Server](define-a-gateway.md).
  
 Si l’homologue auquel vous vous connectez est le contrôleur SBC (Session Border Controller) d’un fournisseur de jonctions SIP (Session Initiation Protocol), assurez-vous qu’il s’agit d’un fournisseur qualifié et qu’il prend en charge la déviation du trafic multimédia. Par exemple, de nombreux fournisseurs de jonctions SIP autoriseront uniquement leurs contrôleurs SBC à recevoir du trafic du serveur de médiation. Dans ce cas, la déviation du trafic doit être activée pour la jonction en question. De même, vous ne pouvez pas activer la déviation du trafic multimédia sauf si l’organisation communique les adresses IP de son réseau interne au fournisseur de jonctions SIP.
  
> [!NOTE]
> La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle RTC, système IP-PBX et SBC. Microsoft a testé une série de passerelles RTC et de SBC avec l’aide de partenaires agréés et a réalisé des tests avec les systèmes IP-PBX de Cisco. Le contournement de média est pris en charge uniquement avec les produits et les versions répertoriés dans [Unified Communications programme Open Interoperability - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
Si vous avez déjà configuré le contrôle d’admission des appels, une autre fonction avancée de Voix Entreprise, notez que la réservation de bande passante effectuée par le contrôle d’admission des appels ne s’applique à aucun appel pour lequel la déviation du trafic multimédia est employée. La vérification de l’emploi de la déviation du trafic multimédia est effectuée en premier, et si elle est employée, le contrôle d’admission des appels n’est pas utilisé pour l’appel. Ce n’est qu’en cas d’échec de la déviation du trafic multimédia que le contrôle d’admission des appels est vérifié. Ces deux fonctions sont, par conséquent, mutuellement exclusives pour tout appel particulier acheminé sur le RTC. Il s’agit du comportement logique, car la déviation du trafic multimédia suppose qu’il n’y a pas de restrictions de bande passante entre les points de terminaison multimédia sur un appel. La déviation du trafic multimédia est impossible sur les liaisons avec bande passante restreinte. Une des deux situations suivantes s’appliquera donc à un appel RTC : a) le trafic multimédia contourne le serveur de médiation, et le contrôle d’admission des appels ne réserve pas de bande passante pour l’appel ; ou b) le contrôle d’admission des appels réserve de la bande passante pour l’appel, et le trafic multimédia est traité par le serveur de médiation impliqué dans l’appel.
  
Outre l’activation de la déviation du trafic multimédia pour des connexions de jonction associées à un homologue, vous devez également configurer les paramètres généraux de déviation du trafic multimédia. Les paramètres généraux de déviation du trafic multimédia peuvent spécifier de toujours tenter la déviation du trafic multimédia pour les appels vers le RTC ou de l’employer en utilisant le mappage des sous-réseaux vers les sites et les régions réseau, ce qui est similaire à ce que fait le contrôle d’admission des appels, une autre fonctionnalité vocale avancée. Lorsque la déviation du trafic multimédia et le contrôle d’admission des appels sont tous les deux activés, les informations relatives aux régions, aux sites et aux sous-réseaux qui sont spécifiées pour le contrôle d’admission des appels sont utilisées automatiquement pour déterminer si la déviation du trafic multimédia doit être employée. Cela signifie que vous ne pouvez pas spécifier de toujours tenter la déviation du trafic multimédia pour les appels vers le RTC lorsque le contrôle d’admission des appels est activé.
  
> [!NOTE]
> Pour configurer la déviation du trafic multimédia en suivant cette procédure, la connectivité entre les clients et l’homologue du serveur de médiation (par exemple, une passerelle RTC, un PBX IP ou un contrôleur SBC d’un fournisseur de jonction SIP [Session Initiation Protocol]) doit être de bonne qualité. Si des restrictions de bande passante sont appliquées sur la liaison, la déviation du trafic multimédia ne peut pas être appliquée aux appels. La déviation du trafic multimédia ne va pas interagir avec chaque passerelle RTC, chaque système IP-PBX et chaque contrôleur SBC. Microsoft a testé une série de passerelles RTC et de SBC avec l’aide de partenaires agréés et a réalisé des tests avec les systèmes IP-PBX de Cisco. Le contournement de média est pris en charge uniquement avec les produits et les versions répertoriés dans [Unified Communications programme Open Interoperability - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
## <a name="deployment-process-for-media-bypass"></a>Procédure de déploiement pour la déviation du trafic multimédia

Le tableau ci-dessous présente une vue d’ensemble de la procédure de déploiement de la déviation du trafic multimédia. 
  
|**Phase**|**Étapes**|**Rôles**|**Documentation de déploiement**|
|:-----|:-----|:-----|:-----|
|Configurer des jonctions pour la déviation du trafic multimédia  <br/> |Si ce n’est déjà fait, configurez une ou plusieurs jonctions pour la déviation du trafic multimédia.  <br/> | Membre du groupe RTCUniversalServerAdmins ou membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator <br/> |[Configurer une jonction avec contournement de média dans Skype pour Business Server](configure-trunk-with-media-bypass.md) <br/> |
|Configurer la déviation du trafic multimédia au niveau global  <br/> |Configurez la déviation du trafic multimédia pour tous les appels vers le réseau téléphonique commuté ou certains appels basés sur les sites et les régions réseau.  <br/> | Membre du groupe RTCUniversalServerAdmins ou membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator <br/> |[Configurer le contournement de média dans Skype pour le serveur d’entreprise pour toujours contourner le serveur de médiation](bypass-the-mediation-server.md) <br/> [Configurer les paramètres globaux de déviation du trafic multimédia dans Skype pour Business Server utilise des informations de sites et aux régions](use-site-and-region-information.md) <br/> |
|Associer des sous-réseaux à des sites réseau, si nécessaire  <br/> |Si vous configurez la déviation du trafic multimédia pour utiliser les informations de site et de région, vous devez associer les sous-réseaux de votre déploiement à des sites et régions réseau (si vous ne l’avez pas déjà fait pour une autre fonctionnalité des communications vocales.)  <br/> | Membre du groupe RTCUniversalServerAdmins ou membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator <br/> |[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
   

