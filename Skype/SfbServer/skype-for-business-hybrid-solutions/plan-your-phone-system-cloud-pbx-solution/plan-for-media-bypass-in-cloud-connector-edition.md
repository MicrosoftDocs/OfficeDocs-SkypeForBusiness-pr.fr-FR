---
title: Planification de la déviation du trafic multimédia dans la version Cloud Connector
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
description: Consultez cette rubrique pour consulter les facteurs de planification pour implémenter la déviation du trafic multimédia avec les versions 2.0 et suivantes de Cloud Connector. Pour plus d’informations sur le déploiement d’une dérivation multimédia, voir déploiement d’une dérivation multimédia dans la version Cloud Connector.
ms.openlocfilehash: 67598cbe31dac074bf360ba6fe1462544fe12c5b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814492"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>Planification de la déviation du trafic multimédia dans la version Cloud Connector
 
Consultez cette rubrique pour consulter les facteurs de planification pour implémenter la déviation du trafic multimédia avec les versions 2.0 et suivantes de Cloud Connector. Pour plus d’informations sur le déploiement d’une dérivation multimédia, voir [déploiement d’une dérivation multimédia dans la version Cloud Connector](deploy-media-bypass-in-cloud-connector.md).
  
Bypass Media permet à un client d’envoyer des contenus multimédias directement sur le tronçon de réseau téléphonique commuté (PSTN), une passerelle ou un contrôleur de bordure de session (SBC), et d’éliminer le composant Cloud Connector édition sur le chemin multimédia.
  
La déviation du trafic multimédia peut améliorer la qualité de la voix en diminuant la latence, la perte de paquets possible et le nombre de points de défaillance éventuels. La suppression du traitement multimédia pour les appels ignorés réduit la charge sur Cloud Connector, qui permet d’utiliser un nombre d’appels simultané plus élevé et peut améliorer l’évolutivité. 
  
 La désactivation de l’option Cloud Connector à partir de tâches de traitement multimédia risque de réduire le nombre de périphériques de connecteur Cloud requis par une infrastructure, donc vous devez activer la dérivation multimédia dans la mesure du possible.
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>Comment la déviation du trafic multimédia influe sur les médias et les voies de signalisation

Bien que la signalisation prenne le même chemin avec ou sans la déviation du trafic multimédia, le trafic multimédia diffère. Les schémas suivants montrent des médias et des voies de signalisation dans des topologies avec et sans déviation du trafic multimédia.   
  
Par exemple, dans la topologie suivante (qui n’utilise pas de contournement multimédia), un client Skype entreprise place un appel RTC sur un numéro externe, le signalement SIP passe à Office 365 et Office 365 appelle le trafic de signalisation en fonction de la voix de l’utilisateur final politique. Pour les utilisateurs du Cloud Connector, la stratégie vocale dirige le trafic de signalisation vers le serveur Edge du Cloud Connector, qui achemine alors le trafic de signalisation vers une passerelle ou un contrôleur de frontière de session PSTN par le biais du serveur de médiation du Cloud Connector. Flux multimédia du client Skype entreprise au serveur de médiation du Cloud Connector, puis à l’SBC ou à la passerelle, comme illustré dans le schéma suivant :
  
**Médias et voies de signalisation sans déviation du trafic multimédia**

![signalisation sans déviation du trafic multimédia](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
Un appel entrant du PSTN utilise le même chemin de signalisation en sens inverse. Pour les utilisateurs internes, le contenu multimédia restera en dernier lieu entre le client Skype entreprise et le serveur de médiation Cloud Connector, puis l’SBC ou la passerelle.
  
Dans la topologie suivante (qui utilise le contournement multimédia), le signalement utilise le même chemin d’accès, mais le contenu multimédia passe directement entre le client Skype entreprise et l’SBC ou la passerelle, comme indiqué dans le schéma suivant :
  
**Médias et voies de signalisation avec déviation du trafic multimédia**

![signalisation avec déviation du trafic multimédia](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>Scénario multisite et déviation du trafic multimédia  

La fonction de contournement de média est également utile lorsque vous souhaitez fournir des services de téléphonie à plusieurs sites à l’aide d’un appareil de connecteur Cloud unique. Dans la mesure où le connecteur Cloud ne peut pas acheminer les appels en fonction des numéros source ou de destination, la plupart des entreprises déploient une connexion SBC ou une passerelle derrière le Cloud Connector pour prendre des décisions de routage Dans ce scénario, la déviation du trafic multimédia élimine le saut entre le client et le SBC central ou la passerelle centrale, comme indiqué sur le schéma ci-après :
  
**Application multisite**

![Exemple multisite de Cloud Connector](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. Le trafic SIP passe de l’utilisateur de Zurich à Office 365.
    
2. Le trafic est alors acheminé vers le dispositif de connexion Cloud d’Amsterdam, tel que spécifié dans la politique de routage vocale de l’utilisateur.
    
3. Le matériel de connexion Cloud dans Amsterdam envoie le trafic SIP à la passerelle centrale d’Amsterdam.
    
4. Dans le cadre de la passerelle centrale d’Amsterdam, vous pouvez prendre les décisions de routage appropriées, puis envoyer le trafic à une SBC ou une passerelle à Zurich, alors que les contenus multimédias sont acheminés directement entre le client Skype entreprise et l’SBC ou la passerelle d’Amsterdam.
    
   Cette approche autorise le déploiement d’autres utilisateurs par le biais d’un déploiement Cloud Connector pour lesquels le Cloud Connector est centralisé. Même si le Cloud Connector est éliminé du chemin d’accès multimédia, dans le cas d’un contenu multimédia de scénario centralisé, il est possible que le contenu du réseau étendu reste parcouru à deux reprises en passant par l’SBC ou la passerelle centralisée.
  
Si un client se trouve en dehors du réseau d’entreprise, le trafic multimédia passe par les serveurs Edge et de médiation du Cloud Connector et du lien réseau étendu entre Zurich et Amsterdam, comme indiqué dans le schéma suivant :
  
![Exemple multisite de Cloud Connector 2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>Clients pris en charge pour la déviation du trafic multimédia

Lors de la première mise en garde du support multimédia, le seul client pris en charge est le client Windows Skype entreprise 2016 intégré à Office 365 ProPlus, version 16.0.7870.2020 ou ultérieure. Les clients peuvent seulement utiliser n'importe quel canal : Actuel, Différé ou Première publication. 
  
> [!NOTE]
> Si vous utilisez une solution VPN de client en combinaison avec le client Skype Entreprise, alors la déviation du trafic multimédia est prise en charge uniquement avec une configuration VPN en tunnels séparés. 
  
Pour plus d’informations sur les canaux de publication, voir [Présentation des canaux de mise à jour d’Office 365 ProPlus](https://support.office.com/en-us/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Pour la version actuelle des clients de canaux différents, voir [les informations de publication des mises à jour d’Office 365 ProPlus](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus). 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>Considérations relatives à la capacité de Cloud Connector avec déviation du trafic multimédia

Sans dérivation multimédia (et en fonction du matériel), un appareil de connecteur Cloud peut gérer de 50 à 500 appels simultanés qui nécessitent le média pour voyager par le biais d’un serveur de médiation. Pour plus d’informations, reportez-vous à la rubrique [planification de Skype entreprise version Cloud Connector](https://technet.microsoft.com/en-us/library/mt605227.aspx). 
  
Avec la déviation du trafic multimédia activée, les clients internes sur la version prise en charge n'utilisent pas le serveur de médiation, donc le nombre de clients internes peut augmenter de manière significative.  
  
Comme indiqué plus haut, les clients externes ou les clients non pris en charge utiliseront le serveur Cloud Connector et les serveurs de médiation pour le média. Lorsque vous calculez le nombre d’appareils de connexion Cloud devant être placés dans un site, vous devez tenir compte des utilisateurs externes et des utilisateurs sur des clients non pris en charge.
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>Cloud Connector prend en charge le mode Always Bypass (Toujours dévier)

Le Cloud Connector prend en charge toujours le mode contournement uniquement. Dans les environnements locaux, il y a deux options : Always Bypass (Toujours dévier) et Use Site and Region Information (Utiliser les informations du site et de la région).
  
Le mode Always Bypass (Toujours dévier) signifie que la déviation du trafic multimédia sera demandée pour tous les appels PSTN avec des clients internes en tant que point d'origine ou de destination. Pour déterminer si le client est interne ou externe, un site web sur la machine virtuelle du serveur de médiation est utilisé. Si le client peut atteindre le site, il est considéré comme interne et la déviation du trafic multimédia est utilisée. Si le client ne peut pas atteindre le site (par exemple le client est sur un réseau domestique), la déviation du trafic multimédia n'est pas utilisée.  
  
Le mode Always Bypass (Toujours dévier) nécessite une connectivité fluide entre les utilisateurs et les passerelles PSTN dans un site PSTN.  
  
Pour plus d’informations, reportez-vous à la rubrique [planification de Skype entreprise version Cloud Connector](https://technet.microsoft.com/en-us/library/mt605227.aspx). 
  
Par exemple, dans le diagramme ci-dessous, les utilisateurs de l’Europe doivent être bien connectés aux trois contrôleurs de frontière de session (SBCs) d’Amsterdam alors que les utilisateurs de l’ouest des États-Unis doivent être bien connectés aux deux SBCs de Seattle. « Bien connectés » signifie qu'ils sont soit situés sur les mêmes sites réseaux que les SBC ou les passerelles, soit connectés par des liaisons WAN disposant d'une bande passante adéquate.
  
![Capacité de Cloud Connector](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> Si un utilisateur de Zurich se rend dans les bureaux de Seattle et que vous souhaitez utiliser le réseau interne pour faire circuler le trafic multimédia entre l'utilisateur en déplacement et les passerelles en Europe (au lieu de passer par internet), alors vous devez vous assurer que les bureaux de Seattle et ceux d'Amsterdam où les SBC ou passerelles européen(nes) sont situé(e)s sont bien connectés. 
  
## <a name="codecs-used-in-media-bypass"></a>Codecs utilisés dans la déviation du trafic multimédia

Lorsque la déviation du trafic multimédia est activée, le trafic multimédia entre un client et un SBC ou une passerelle utilise le codec G.711.  
  
## <a name="see-also"></a>Voir aussi

[Contournement du déploiement multimédia dans la version Cloud Connector](deploy-media-bypass-in-cloud-connector.md)
