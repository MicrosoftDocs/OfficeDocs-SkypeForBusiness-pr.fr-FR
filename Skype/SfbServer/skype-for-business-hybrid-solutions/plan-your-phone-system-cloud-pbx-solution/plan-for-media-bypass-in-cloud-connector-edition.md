---
title: Planification de la déviation du trafic multimédia dans Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: Lisez cette rubrique pour examiner les considérations relatives à la planification de l’implémentation de la déviation du trafic multimédia avec la version 2,0 et ultérieure de Cloud Connector. Pour plus d’informations sur le déploiement de la déviation du trafic multimédia, voir deploy Media Bypass in Cloud Connector Edition.
ms.openlocfilehash: 47b8d9e5d0b69b95c48f89591d75d53591b7426c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010307"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>Planification de la déviation du trafic multimédia dans Cloud Connector Edition
 
Lisez cette rubrique pour examiner les considérations relatives à la planification de l’implémentation de la déviation du trafic multimédia avec la version 2,0 et ultérieure de Cloud Connector. Pour plus d’informations sur le déploiement de la déviation du trafic multimédia, voir [Deploy Media Bypass in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md).
  
La déviation du trafic multimédia permet à un client d’envoyer directement des médias au tronçon suivant du réseau téléphonique commuté (RTC), à savoir un contrôleur de frontière de session ou un contrôleur SBC (session Border Controller) et d’éliminer le composant Cloud Connector Edition du chemin de média.
  
La déviation du trafic multimédia peut améliorer la qualité de la voix en diminuant la latence, le risque de perte de paquets et le nombre de points de défaillance potentiels. L’élimination du traitement multimédia pour les appels contournés réduit la charge sur Cloud Connector, ce qui permet un nombre d’appels simultanés plus élevé et peut améliorer l’extensibilité. 
  
 La libération de Cloud Connector à partir de tâches de traitement multimédia peut réduire le nombre d’appareils Cloud Connector dont une infrastructure a besoin, de sorte que vous devez activer la déviation du trafic multimédia dès que possible.
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>Impact de la déviation du trafic multimédia sur les voies de signalisation et de signalisation

Bien que la signalisation prenne le même chemin avec ou sans déviation du trafic multimédia, le flux multimédia diffère. Les diagrammes suivants indiquent les médias et les voies de signalisation dans des topologies avec et sans déviation du trafic multimédia. 
  
Par exemple, dans la topologie suivante, qui n’utilise pas le contournement de média, un client Skype entreprise passe un appel RTC à un numéro externe, la signalisation SIP vers Office 365 et Office 365 dirige le trafic de signalisation en fonction de la voix de l’utilisateur final renvoi. Pour les utilisateurs de Cloud Connector, la stratégie de voix dirige le trafic de signalisation vers le serveur Edge de Cloud Connector, qui achemine ensuite le trafic de signalisation vers un contrôleur SBC (session Border Controller) ou une passerelle via le serveur de médiation Cloud Connector. Le flux multimédia s’achemine du client Skype entreprise vers le serveur de médiation Cloud Connector, puis vers le SBC ou la passerelle, comme illustré dans le diagramme suivant :
  
**Médias et voies de signalisation sans déviation du trafic multimédia**

![signalisation sans déviation du trafic multimédia](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
Un appel entrant du RTC utilise le même chemin de signalisation en sens inverse. Pour les utilisateurs internes, les médias sont toujours acheminés entre le client Skype entreprise et le serveur de médiation Cloud Connector, puis l’SBC ou la passerelle.
  
Dans la topologie suivante, qui utilise la déviation du trafic multimédia, la signalisation prend le même chemin d’accès, mais le trafic multimédia est directement transféré entre le client Skype entreprise et l’SBC ou la passerelle, comme illustré dans le diagramme suivant :
  
**Médias et voies de signalisation avec déviation du trafic multimédia**

![signalisation avec déviation du trafic multimédia](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>Scénario multisite et déviation du trafic multimédia

La déviation du trafic multimédia est également utile lorsque vous souhaitez fournir des services de téléphonie à plusieurs sites à l’aide d’une seule Appliance Cloud Connector. Dans la mesure où Cloud Connector ne peut pas acheminer les appels en fonction des numéros de source ou de destination, la plupart des entreprises déploient un SBC ou une passerelle derrière Cloud Connector pour prendre des décisions de routage. La déviation du trafic multimédia dans ce scénario élimine le tronçon entre le client et la SBC ou la passerelle centrale, comme illustré dans le diagramme suivant :
  
**Application multisite**

![Exemple multisite de Cloud Connector](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. Le trafic SIP passe de l’utilisateur à Zurich à Office 365.
    
2. Le trafic est ensuite acheminé vers l’appliance Cloud Connector à Amsterdam, comme spécifié dans la stratégie de routage des communications vocales de l’utilisateur.
    
3. L’appliance Cloud Connector d’Amsterdam envoie le trafic SIP à la passerelle centrale à Amsterdam.
    
4. La passerelle centrale d’Amsterdam prend les décisions de routage appropriées, puis envoie le trafic vers un SBC ou une passerelle à Zurich, tandis que les médias transitent directement entre le client Skype entreprise et le SBC ou la passerelle à Amsterdam.
    
   Cette approche permet de traiter un plus grand nombre d’utilisateurs par un déploiement Cloud Connector où Cloud Connector est centralisé. Même si Cloud Connector est éliminé du chemin multimédia, un support de scénario multisite centralisé peut toujours traverser le réseau étendu (WAN) à deux reprises, comme requis pour circuler via l’SBC ou la passerelle centralisée.
  
Si un client se trouve à l’extérieur du réseau d’entreprise à l’aide d’un appel sortant, le trafic multimédia transite via les serveurs Edge et de médiation de Cloud Connector et de la liaison de réseau étendu entre Zurich et Amsterdam, comme illustré dans le diagramme suivant :
  
![Exemple multisite de Cloud Connector 2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>Clients pris en charge pour la déviation du trafic multimédia

Avec la première publication de la déviation du trafic multimédia, le seul client pris en charge est le client Windows Skype entreprise 2016 qui fait partie d’Office 365 ProPlus, version 16.0.7870.2020 ou supérieure. Les clients peuvent utiliser n’importe quel canal : actuel, différé ou première publication différée. 
  
> [!NOTE]
> Si vous utilisez une solution VPN client en combinaison avec le client Skype entreprise, la déviation du trafic multimédia n’est prise en charge qu’avec une configuration de tunneling VPN. 
  
Pour plus d’informations sur les canaux de publication, voir [vue d’ensemble des canaux de mise à jour pour Office 365 ProPlus](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Pour la version actuelle des clients dans différents canaux, consultez la rubrique [Release information for Updates to Office 365 ProPlus](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus). 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>Considérations relatives à la capacité de Cloud Connector avec contournement de média

Sans déviation du trafic multimédia — et en fonction du matériel — une appliance Cloud Connector peut gérer entre 50 et 500 appels simultanés qui nécessitent que les médias transitent via un serveur de médiation. Pour plus d’informations, reportez-vous à la rubrique [plan for Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605227.aspx). 
  
Lorsque la déviation du trafic multimédia est activée, les clients internes sur la version prise en charge n’utilisent pas le serveur de médiation, de sorte que le nombre de clients internes peut augmenter de manière significative. 
  
Comme indiqué ci-dessus, les clients externes ou les clients non pris en charge utiliseront les serveurs Edge et de médiation Cloud Connector pour les médias. Lors du calcul du nombre d’appliances Cloud Connector devant être placées dans un site, vous devez prendre en compte le trafic provenant d’utilisateurs et d’utilisateurs externes sur les clients non pris en charge.
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>Cloud Connector prend en charge toujours le mode contournement

Cloud Connector prend en charge toujours le mode contournement uniquement. Dans les environnements locaux, il existe deux options : toujours outrepasser et utiliser les informations de site et de région.
  
Toujours Bypass signifie que la tentative de contournement de média est tentée pour tous les appels RTC avec des clients internes en tant qu’origine ou point de destination. Pour déterminer si le client est interne ou externe, un site Web sur la machine virtuelle du serveur de médiation est utilisé. Si le client peut atteindre le site, il est considéré comme étant interne et la déviation du trafic multimédia est utilisée. Si le client ne peut pas atteindre le site (par exemple, le client se trouve sur un réseau domestique), la déviation du trafic multimédia n’est pas utilisée. 
  
Toujours Bypass nécessite une connectivité sans obstruction entre les utilisateurs et les passerelles RTC au sein d’un site RTC. 
  
Pour plus d’informations, reportez-vous à la rubrique [plan for Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605227.aspx). 
  
Par exemple, dans le diagramme ci-dessous, les utilisateurs européens doivent être correctement connectés aux trois contrôleurs de frontière de session (SBC) dans Amsterdam, tandis que les utilisateurs de l’Ouest doivent être correctement connectés aux deux contrôleurs de frontière de session de Seattle. Bien connecté signifie qu’il se trouve dans les mêmes sites réseau que les contrôleurs SBC ou les passerelles, ou sur des liaisons de réseau étendu ayant une bande passante adéquate.
  
![Capacité de Cloud Connector](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> Si un utilisateur de Zurich se déplace vers le Bureau de Seattle et que vous souhaitez utiliser le réseau interne pour transmettre le trafic multimédia entre l’utilisateur itinérant et les passerelles en Europe (au lieu de passer sur Internet), vous devez vous assurer que les bureaux de Seattle et d’Amsterdam Office où les contrôleurs SBC ou les passerelles européens sont qualifiés d’une bonne connexion. 
  
## <a name="codecs-used-in-media-bypass"></a>Codecs utilisés dans la déviation du trafic multimédia

Lorsque la déviation du trafic multimédia est activée, le trafic multimédia entre un client et un SBC ou une passerelle utilise le codec G. 711. 
  
## <a name="see-also"></a>Voir aussi

[Déploiement de la déviation du trafic multimédia dans Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)
