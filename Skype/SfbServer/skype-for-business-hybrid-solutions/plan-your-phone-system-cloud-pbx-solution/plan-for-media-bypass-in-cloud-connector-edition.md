---
title: Planification de la déviation du trafic multimédia dans la version Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: Consultez cette rubrique pour consulter les facteurs de planification pour implémenter la déviation du trafic multimédia avec les versions 2.0 et suivantes de Cloud Connector. Pour plus d’informations sur le déploiement de media ignorer, voir support de déploiement à ignorer dans le nuage lien édition.
ms.openlocfilehash: bf659b7ea7b872a09e8c8ce2358c04cde2ba11d7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>Planification de la déviation du trafic multimédia dans la version Cloud Connector
 
Consultez cette rubrique pour consulter les facteurs de planification pour implémenter la déviation du trafic multimédia avec les versions 2.0 et suivantes de Cloud Connector. Pour plus d’informations sur le déploiement de media ignorer, voir [déployer media ignore dans le nuage lien édition](deploy-media-bypass-in-cloud-connector.md).
  
Le contournement de média permet au client d’envoyer le CD directement sur le tronçon suivant de commutation de téléphone RTPC (réseau Public), une passerelle ou un contrôleur de Session en périphérie (SBC) — et d’éliminer le composant d’édition de connecteur de nuage du chemin d’accès de média.
  
La déviation du trafic multimédia peut améliorer la qualité de la voix en diminuant la latence, la perte de paquets possible et le nombre de points de défaillance éventuels. Élimination de support de traitement des appels ignorées réduit la charge sur le connecteur de Cloud, ce qui permet un nombre plus élevé d’appels simultanés, et peut améliorer l’évolutivité. 
  
 Libération de connecteur de nuage à partir des tâches de traitement de support peut réduire le nombre de matériels de connecteur de nuage que requiert d’une infrastructure, donc vous devez activer le contournement de média dès que possible.
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>Comment la déviation du trafic multimédia influe sur les médias et les voies de signalisation

Bien que la signalisation prenne le même chemin avec ou sans la déviation du trafic multimédia, le trafic multimédia diffère. Les schémas suivants montrent des médias et des voies de signalisation dans des topologies avec et sans déviation du trafic multimédia.  
  
Par exemple, dans la topologie est la suivante, qui n’ignore pas les médias utilisent — un Skype pour client d’entreprise place un appel RTC à un numéro externe, la signalisation SIP va vers Office 365 et Office 365 dirige ensuite le trafic de signalisation en fonction de la voix de l’utilisateur final stratégie. Pour les utilisateurs du connecteur du nuage, la stratégie voice dirige le trafic de signalisation pour le serveur Edge de connecteur Cloud, qui route le trafic de signalisation à un contrôleur de bordure de Session RTC (SBC) ou une passerelle via le serveur de médiation de connecteur de nuage. Media provient le Skype pour client d’entreprise sur le serveur de médiation de connecteur de nuage, puis à la colonie d’abeilles simulée ou une passerelle, comme illustré dans le diagramme suivant :
  
**Ignorent les supports et voies de signalisation sans support**

![signalisation sans déviation du trafic multimédia](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
Un appel entrant du PSTN utilise le même chemin de signalisation en sens inverse. Pour les utilisateurs internes, media iront toujours en fin de compte entre le Skype pour client d’entreprise et le serveur de médiation de connecteur de nuage et puis la colonie d’abeilles simulée ou passerelle.
  
Dans la topologie suivante : qui contournent utilisent media : signalisation prend le même chemin, mais media circule directement entre le Skype pour le Business et la colonie d’abeilles simulée ou passerelle, comme illustré dans le diagramme suivant :
  
**Ignorent les médias et les voies de signalisation avec media**

![signalisation avec déviation du trafic multimédia](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>Scénario multisite et déviation du trafic multimédia

Le contournement de média est également utile lorsque vous souhaitez fournir des services de téléphonie sur plusieurs sites à l’aide d’une seule appliance de connecteur de nuage. Étant donné que le nuage connecteur ne peut pas acheminer les appels basés sur les valeurs de source ou de destination, la plupart des entreprises déployer un SBC ou une passerelle derrière le connecteur du nuage pour prendre des décisions de routage. Dans ce scénario, la déviation du trafic multimédia élimine le saut entre le client et le SBC central ou la passerelle centrale, comme indiqué sur le schéma ci-après :
  
**Application de plusieurs sites**

![Exemple multisite de Cloud Connector](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. Le trafic SIP passe de l’utilisateur à Zurich vers Office 365.
    
2. Le trafic s’achemine ensuite à l’appliance de connecteur de nuage à Amsterdam comme spécifié dans la stratégie de routage utilisateur vocale.
    
3. La solution matérielle-logicielle connecteur de nuage à Amsterdam envoie le trafic SIP vers la passerelle centrale à Amsterdam.
    
4. La passerelle centrale à Amsterdam prend les décisions de routage appropriées et envoie ensuite le trafic vers un SBC ou une passerelle à Zurich, lors du flux de média directement entre le Skype pour Business et SBC ou passerelle à Amsterdam.
    
 Cette approche permet de servir plus d’utilisateurs par un déploiement de connecteur de nuage où le connecteur du nuage est centralisée. Même si le connecteur du nuage est éliminé du chemin d’accès de média, dans un scénario à plusieurs sites centralisé media peut-être toujours parcourir le réseau WAN deux fois en tant que doit traverser le SBC centralisée ou une passerelle.
  
Si un client est à l’extérieur du réseau d’entreprise un appel sortant, le media flux de trafic via les serveurs Edge et médiation de lien de connecteur du nuage et de réseau étendu entre Zurich et Amsterdam, comme illustré dans le diagramme suivant :
  
![Exemple multisite de Cloud Connector 2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>Clients pris en charge pour la déviation du trafic multimédia

Dans la première version de contournement de média, le seul client pris en charge est le Skype pour entreprise 2016 Windows Client qui fait partie d’Office 365 ProPlus, version 16.0.7870.2020 ou supérieure. Les clients peuvent seulement utiliser n'importe quel canal : Actuel, Différé ou Première publication. 
  
> [!NOTE]
> Si vous utilisez une solution VPN de client en combinaison avec le client Skype Entreprise, alors la déviation du trafic multimédia est prise en charge uniquement avec une configuration VPN en tunnels séparés. 
  
Pour plus d’informations sur les chaînes de version, consultez [la vue d’ensemble de canaux de mise à jour pour Office 365 ProPlus](https://support.office.com/en-us/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Pour la version actuelle des clients de différents canaux, consultez [client Office 365 à jour des versions de canal](https://technet.microsoft.com/en-us/office/mt465751.aspx). 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>Considérations relatives à la capacité de Cloud Connector avec déviation du trafic multimédia

Sans ignore des media et en fonction du matériel — une appliance de connecteur de nuage peut gérer de 50 à 500 appels simultanés nécessitant un support à transiter sur un serveur de médiation. Pour plus d’informations, reportez-vous à la section [planifier Skype pour connecteur de Cloud Business Edition](https://technet.microsoft.com/en-us/library/mt605227.aspx). 
  
Avec la déviation du trafic multimédia activée, les clients internes sur la version prise en charge n'utilisent pas le serveur de médiation, donc le nombre de clients internes peut augmenter de manière significative. 
  
Comme indiqué ci-dessus, les clients externes ou non pris en charge utilise les serveurs Edge de connecteur de nuage et de médiation pour media. Lors du calcul de combien d’appliances nuage connecteur doit être placé dans un site, vous devez prendre en compte le trafic des utilisateurs externes et aux utilisateurs de clients non pris en charge.
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>Cloud Connector prend en charge le mode Always Bypass (Toujours dévier)

Connecteur de nuage prend en charge uniquement en mode Ignorer toujours. Dans les environnements locaux, il y a deux options : Always Bypass (Toujours dévier) et Use Site and Region Information (Utiliser les informations du site et de la région).
  
Le mode Always Bypass (Toujours dévier) signifie que la déviation du trafic multimédia sera demandée pour tous les appels PSTN avec des clients internes en tant que point d'origine ou de destination. Pour déterminer si le client est interne ou externe, un site web sur la machine virtuelle du serveur de médiation est utilisé. Si le client peut atteindre le site, il est considéré comme interne et la déviation du trafic multimédia est utilisée. Si le client ne peut pas atteindre le site (par exemple le client est sur un réseau domestique), la déviation du trafic multimédia n'est pas utilisée.  
  
Le mode Always Bypass (Toujours dévier) nécessite une connectivité fluide entre les utilisateurs et les passerelles PSTN dans un site PSTN.  
  
Pour plus d’informations, reportez-vous à la section [planifier Skype pour connecteur de Cloud Business Edition](https://technet.microsoft.com/en-us/library/mt605227.aspx). 
  
Par exemple, dans le schéma ci-dessous, les utilisateurs en Europe doivent être reliés correctement aux trois Session bordure contrôleurs (SBCs) d’Amsterdam tandis que les utilisateurs nous ouest doivent être bien connectés pour les deux SBCs à Seattle. « Bien connectés » signifie qu'ils sont soit situés sur les mêmes sites réseaux que les SBC ou les passerelles, soit connectés par des liaisons WAN disposant d'une bande passante adéquate.
  
![Capacité de Cloud Connector](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> Si un utilisateur de Zurich se rend dans les bureaux de Seattle et que vous souhaitez utiliser le réseau interne pour faire circuler le trafic multimédia entre l'utilisateur en déplacement et les passerelles en Europe (au lieu de passer par internet), alors vous devez vous assurer que les bureaux de Seattle et ceux d'Amsterdam où les SBC ou passerelles européen(nes) sont situé(e)s sont bien connectés. 
  
## <a name="codecs-used-in-media-bypass"></a>Codecs utilisés dans la déviation du trafic multimédia

Lorsque la déviation du trafic multimédia est activée, le trafic multimédia entre un client et un SBC ou une passerelle utilise le codec G.711. 
  
## <a name="see-also"></a>Voir aussi

#### 

[Déployer le contournement de média dans le nuage lien édition](deploy-media-bypass-in-cloud-connector.md)

