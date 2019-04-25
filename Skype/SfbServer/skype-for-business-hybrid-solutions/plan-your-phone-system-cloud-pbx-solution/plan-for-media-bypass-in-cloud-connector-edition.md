---
title: Planification de la déviation du trafic multimédia dans la version Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: Consultez cette rubrique pour consulter les facteurs de planification pour implémenter la déviation du trafic multimédia avec les versions 2.0 et suivantes de Cloud Connector. Pour plus d’informations sur le déploiement de médias contournement de média, voir Deploy multimédia dans le nuage connecteur Edition de contournement.
ms.openlocfilehash: 6ddaec00925d5eea7d7c82d89f0324958c87abb9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238825"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>Planification de la déviation du trafic multimédia dans la version Cloud Connector
 
Consultez cette rubrique pour consulter les facteurs de planification pour implémenter la déviation du trafic multimédia avec les versions 2.0 et suivantes de Cloud Connector. Pour plus d’informations sur le déploiement de médias contournement de média, voir [déployer le contournement de média dans le nuage connecteur Edition](deploy-media-bypass-in-cloud-connector.md).
  
Le contournement de média permet au client d’envoyer des données multimédia directement au saut suivant Public réseau de téléphonique commuté (RTC) — une passerelle ou un contrôleur de Session en périphérie (SBC) — et d’éliminer le composant nuage connecteur Edition à partir du chemin d’accès des médias.
  
La déviation du trafic multimédia peut améliorer la qualité de la voix en diminuant la latence, la perte de paquets possible et le nombre de points de défaillance éventuels. Élimination des médias de traitement pour les appels ignorés réduit la charge sur le nuage connecteur, ce qui permet à un nombre d’appels simultanés, et permettre améliorer l’extensibilité. 
  
 Libération nuage connecteur à partir des tâches de traitement multimédia peut réduire le nombre d’appareils de nuage connecteur qu'une infrastructure nécessite, afin que vous devez activer le contournement de média autant que possible.
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>Comment la déviation du trafic multimédia influe sur les médias et les voies de signalisation

Bien que la signalisation prenne le même chemin avec ou sans la déviation du trafic multimédia, le trafic multimédia diffère. Les schémas suivants montrent des médias et des voies de signalisation dans des topologies avec et sans déviation du trafic multimédia.   
  
Par exemple, dans la topologie suivante : qui n’ignore pas les médias utilisent — une Skype pour Business client effectue un appel PSTN vers un numéro externe, la signalisation SIP accède à Office 365 et Office 365 puis la dirige le trafic de signalisation en fonction de la voix de l’utilisateur final stratégie. Pour les utilisateurs de nuage connecteur, la stratégie de voix dirige le trafic de signalisation pour le serveur Edge sur le nuage connecteur, puis achemine le trafic de signalisation à un contrôleur de frontière de Session RTC (SBC) ou une passerelle via le serveur de médiation dans le nuage connecteur. Multimédia s’enchaîne de la Skype pour client d’entreprise pour le serveur de médiation dans le nuage connecteur, puis vers le contrôleur SBC ou passerelle, comme indiqué dans le diagramme suivant :
  
**Médias et voies de signalisation sans déviation du trafic multimédia**

![signalisation sans déviation du trafic multimédia](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
Un appel entrant du PSTN utilise le même chemin de signalisation en sens inverse. Pour les utilisateurs internes, seront toujours finalement flux des médias entre le Skype pour client d’entreprise et le serveur de médiation dans le nuage connecteur puis le contrôleur SBC ou passerelle.
  
Dans la topologie suivante : qui utilisent le contournement de média : signalisation prend le même chemin d’accès, mais les données multimédias transitent directement entre le Skype pour client d’entreprise et SBC ou passerelle, comme illustré dans le diagramme suivant :
  
**Médias et voies de signalisation avec déviation du trafic multimédia**

![signalisation avec déviation du trafic multimédia](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>Scénario multisite et déviation du trafic multimédia  

Le contournement de média est également utile lorsque vous souhaitez fournir des services de téléphonie sur plusieurs sites à l’aide d’une solution de nuage connecteur unique. Comme dans le nuage connecteur ne peut pas acheminer les appels en fonction de leur source ou de destination, la plupart des entreprises déploient un contrôleur SBC ou une passerelle derrière nuage connecteur pour prendre des décisions de routage. Dans ce scénario, la déviation du trafic multimédia élimine le saut entre le client et le SBC central ou la passerelle centrale, comme indiqué sur le schéma ci-après :
  
**Application multisite**

![Exemple multisite de Cloud Connector](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. Le trafic SIP s’enchaîne de l’utilisateur à Zurich vers Office 365.
    
2. Le trafic achemine ensuite à la solution de nuage connecteur à Amsterdam tel que spécifié dans la stratégie de routage voix utilisateur.
    
3. La solution de nuage connecteur à Amsterdam envoie le trafic SIP vers la passerelle centrale à Amsterdam.
    
4. La passerelle centrale à Amsterdam prend les décisions de routage appropriées et envoie ensuite le trafic à un contrôleur SBC ou une passerelle à Zurich, tout en flux multimédias directement entre le Skype pour Business et SBC ou passerelle à Amsterdam.
    
   Cette approche permet de traiter davantage d’utilisateurs par un déploiement en nuage connecteur où nuage connecteur est centralisée. Même si le nuage connecteur est éliminé du chemin d’accès des médias, dans un scénario de plusieurs site centralisé multimédia peut toujours parcourir le réseau étendu à deux reprises selon les besoins de flux via le contrôleur SBC centralisée ou une passerelle.
  
Si un client est en dehors du réseau d’entreprise un appel sortant, le trafic multimédia transite via les serveurs de périphérie et de médiation du lien de nuage connecteur et des liaisons réseau étendu entre Zurich et Amsterdam, comme illustré dans le diagramme suivant :
  
![Exemple multisite de Cloud Connector 2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>Clients pris en charge pour la déviation du trafic multimédia

Dans la première version du contournement de média, le seul client pris en charge est la Skype pour Business 2016 Windows Client qui fait partie d’Office 365 ProPlus, version 16.0.7870.2020 ou ultérieure. Les clients peuvent seulement utiliser n'importe quel canal : Actuel, Différé ou Première publication. 
  
> [!NOTE]
> Si vous utilisez une solution VPN de client en combinaison avec le client Skype Entreprise, alors la déviation du trafic multimédia est prise en charge uniquement avec une configuration VPN en tunnels séparés. 
  
Pour plus d’informations sur les canaux de version, voir [vue d’ensemble des canaux de mise à jour pour Office 365 ProPlus](https://support.office.com/en-us/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Pour la version actuelle des clients de différents canaux, voir [Release des informations mises à jour pour Office 365 ProPlus](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus). 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>Considérations relatives à la capacité de Cloud Connector avec déviation du trafic multimédia

Sans contournement de média et en fonction du matériel — une appliance nuage connecteur peut gérer de 50 à 500 appels simultanés nécessitant multimédia permettent de parcourir un serveur de médiation. Pour plus d’informations, voir [planifier Skype pour l’édition de connecteur Business Cloud](https://technet.microsoft.com/en-us/library/mt605227.aspx). 
  
Avec la déviation du trafic multimédia activée, les clients internes sur la version prise en charge n'utilisent pas le serveur de médiation, donc le nombre de clients internes peut augmenter de manière significative.  
  
Comme mentionné ci-dessus, les clients externes ou non prises en charge de clients utilisera les serveurs Edge du connecteur sur le nuage et de médiation pour le média. Lors du calcul de combien d’appliances nuage connecteur doit être placé dans un site, vous devez prendre en compte le trafic en provenance des utilisateurs externes et sur les clients non pris en charge.
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>Cloud Connector prend en charge le mode Always Bypass (Toujours dévier)

Nuage connecteur prend en charge uniquement en mode toujours ignorer. Dans les environnements locaux, il y a deux options : Always Bypass (Toujours dévier) et Use Site and Region Information (Utiliser les informations du site et de la région).
  
Le mode Always Bypass (Toujours dévier) signifie que la déviation du trafic multimédia sera demandée pour tous les appels PSTN avec des clients internes en tant que point d'origine ou de destination. Pour déterminer si le client est interne ou externe, un site web sur la machine virtuelle du serveur de médiation est utilisé. Si le client peut atteindre le site, il est considéré comme interne et la déviation du trafic multimédia est utilisée. Si le client ne peut pas atteindre le site (par exemple le client est sur un réseau domestique), la déviation du trafic multimédia n'est pas utilisée.  
  
Le mode Always Bypass (Toujours dévier) nécessite une connectivité fluide entre les utilisateurs et les passerelles PSTN dans un site PSTN.  
  
Pour plus d’informations, voir [planifier Skype pour l’édition de connecteur Business Cloud](https://technet.microsoft.com/en-us/library/mt605227.aspx). 
  
Par exemple, dans le diagramme ci-dessous, les utilisateurs en Europe doivent être correctement connectés pour les trois contrôleurs de frontière de Session (SBC) à Amsterdam alors que nous ouest utilisateurs doivent être correctement connectés pour les deux SBCs de Seattle. « Bien connectés » signifie qu'ils sont soit situés sur les mêmes sites réseaux que les SBC ou les passerelles, soit connectés par des liaisons WAN disposant d'une bande passante adéquate.
  
![Capacité de Cloud Connector](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> Si un utilisateur de Zurich se rend dans les bureaux de Seattle et que vous souhaitez utiliser le réseau interne pour faire circuler le trafic multimédia entre l'utilisateur en déplacement et les passerelles en Europe (au lieu de passer par internet), alors vous devez vous assurer que les bureaux de Seattle et ceux d'Amsterdam où les SBC ou passerelles européen(nes) sont situé(e)s sont bien connectés. 
  
## <a name="codecs-used-in-media-bypass"></a>Codecs utilisés dans la déviation du trafic multimédia

Lorsque la déviation du trafic multimédia est activée, le trafic multimédia entre un client et un SBC ou une passerelle utilise le codec G.711.  
  
## <a name="see-also"></a>Voir aussi

[Déployer le contournement de média dans le nuage connecteur Edition](deploy-media-bypass-in-cloud-connector.md)
