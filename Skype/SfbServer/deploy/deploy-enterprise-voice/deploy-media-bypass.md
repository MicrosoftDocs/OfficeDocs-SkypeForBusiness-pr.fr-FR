---
title: Déployer le contournement de média dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
description: Déployez le contournement de média dans Skype Entreprise Server Voix Entreprise. Comprend les conditions préalables et la liste de contrôle du processus de déploiement.
ms.openlocfilehash: d1815b0ec76bed3aa0da9be52a2eeceb0c29b49d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62400708"
---
# <a name="deploy-media-bypass-in-skype-for-business-server"></a>Déployer le contournement de média dans Skype Entreprise Server
 
Déployez le contournement de média dans Skype Entreprise Server Voix Entreprise. Comprend les conditions préalables et la liste de contrôle du processus de déploiement.
  
Cette rubrique suppose que vous avez déjà publié et configuré au moins un ou plusieurs serveurs de médiation et au moins un homologue de passerelle pour fournir une connectivité PSTN. Pour plus d’informations sur ces tâches, voir [Deploy a Mediation Server in Topology Builder in Skype Entreprise Server](deploy-a-mediation-server.md) and [Define a gateway in Topology Builder in Skype Entreprise Server](define-a-gateway.md).
  
 Si l’homologue à qui vous vous connectez est le SBC d’un fournisseur de trunking SIP, assurez-vous qu’il s’agit d’un fournisseur qualifié et qu’il prend en charge le contournement de média. Par exemple, de nombreux fournisseurs de jonction SIP autoriseront uniquement leurs SBC à recevoir du trafic du serveur de médiation. Dans ce cas, le contournement doit être activé pour la jonction en question. De même, vous ne pouvez pas activer le contournement de média, à moins que l’organisation ne révèle les adresses IP de son réseau interne au fournisseur de jonctions SIP.
  
> [!NOTE]
> Le contournement de média ne fonctionnera pas avec chaque passerelle PSTN, système IP-PBX et SBC. Microsoft a testé un ensemble de passerelles PSTN et de SCS avec des partenaires certifiés et a effectué des tests avec des PBX IP Cisco. Le contournement de média est pris en charge uniquement avec les produits et versions répertoriés dans le programme d’interopérabilité d’ouverture des communications unifiées [( Lync Server](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)). 
  
Si vous avez déjà configuré le contrôle d’admission des appels (CAC), une autre fonction avancée de Voix Entreprise, notez que la réservation de bande passante effectuée par le contrôle d’admission des appels ne s’applique à aucun appel pour lequel le contournement de média est employé. La vérification de l’emploi du contournement de media est effectuée en premier, et s’il est employé, le contrôle d’admission des appels n’est pas utilisé pour l’appel ; ce n’est qu’en cas d’échec du contournement de média que le contrôle d’admission des appels est vérifié. Ces deux fonctions sont par conséquent mutuellement exclusives pour tout appel particulier qui est acheminé sur le PSTN. Il s’agit du comportement logique car le contournement de média suppose que les restrictions de bande passante n’existent pas entre systèmes d’extrémité de média sur un appel ; le contournement de média est impossible sur les liaisons avec bande passante restreinte. Une des deux situations suivantes s’appliquera donc à un appel PSTN : a) le média contourne le serveur de médiation, et le contrôle d’admission des appels ne réserve pas de bande passante pour l’appel ; ou b) le contrôle d’admission des appels réserve de la bande passante pour l’appel, et le media est traité par le serveur de médiation impliqué dans l’appel.
  
En plus d’activer le contournement de média pour des connexions de jonction associées à un homologue, vous devez également configurer les paramètres globaux du contournement de média. Les paramètres globaux de déviation du média peuvent spécifier que la déviation du média est toujours tentée pour les appels vers le réseau téléphonique public public (PSTN) ou que la déviation du média est employée à l’aide du mappage des sous-réseaux aux sites réseau et aux régions réseau, comme le fait le contrôle d’admission des appels, une autre fonctionnalité vocale avancée. Lorsque le contournement de média et le contrôle d’admission des appels sont tous deux activés, les informations de région réseau, de site réseau et de sous-réseau spécifiées pour le contrôle d’admission des appels sont automatiquement utilisées pour déterminer s’il faut utiliser le contournement de média. Cela signifie que vous ne pouvez pas spécifier que le contournement de média est toujours tenté pour les appels vers le réseau téléphonique téléphonique public (PSTN) lorsque le contrôle d’admission des appels est activé.
  
> [!NOTE]
> Pour configurer le contournement de média en suivant cette procédure, la connectivité entre les clients et l’homologue du serveur de médiation (par exemple, une passerelle PSTN, un PBX IP ou un contrôleur de frontière de session d’un fournisseur de jonction SIP) doit être bonne. Si des restrictions de bande passante sont appliquées sur la liaison, le contournement de média ne peut pas être appliqué aux appels. Le contournement de média ne va pas interagir avec chaque passerelle PSTN, chaque système IP-PBX et chaque SBC. Microsoft a testé un ensemble de passerelles PSTN et de SCS avec des partenaires certifiés et a effectué des tests avec des PBX IP Cisco. Le contournement de média est pris en charge uniquement avec les produits et versions répertoriés dans le programme d’interopérabilité d’ouverture des communications unifiées [( Lync Server](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)). 
  
## <a name="deployment-process-for-media-bypass"></a>Processus de déploiement pour le contournement de média

Le tableau suivant fournit une vue d’ensemble du processus de déploiement du contournement de média. 
  
|**Étape**|**Étapes**|**Rôles**|**Documentation de déploiement**|
|:-----|:-----|:-----|:-----|
|Configurer des trunks pour le contournement de média  <br/> |Si ce n’est pas déjà fait, configurez une ou plusieurs trunks pour le contournement de média.  <br/> | Membre du groupe RTCUniversalServerAdmins ou membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator <br/> |[Configurer une trunk avec déviation du média dans Skype Entreprise Server](configure-trunk-with-media-bypass.md) <br/> |
|Configurer le contournement de média globalement  <br/> |Configurez le contournement de média pour tous les appels vers le réseau téléphonique téléphonique public (PSTN) ou certains appels basés sur des sites réseau et des régions réseau.  <br/> | Membre du groupe RTCUniversalServerAdmins ou membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator <br/> |[Configurer le contournement de média dans Skype Entreprise Server pour toujours contourner le serveur de médiation](bypass-the-mediation-server.md) <br/> [Configurer les paramètres globaux de contournement de média dans Skype Entreprise Server pour utiliser les informations de site et de région](use-site-and-region-information.md) <br/> |
|Associer des sous-réseaux à des sites réseau, si nécessaire  <br/> |Si vous configurez le contournement de média pour utiliser les informations de site et de région, vous devez associer les sous-réseaux de votre déploiement aux sites et régions réseau (si vous ne l’avez pas déjà fait pour une autre fonctionnalité vocale).)  <br/> | Membre du groupe RTCUniversalServerAdmins ou membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator <br/> |[Associer un sous-réseau à un site réseau](deploy-network.md#BKMK_AssociateSubnets) <br/> |
