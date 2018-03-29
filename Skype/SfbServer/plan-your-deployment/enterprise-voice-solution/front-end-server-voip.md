---
title: Composants VoIP de serveur frontal pour Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: Obtenir des informations sur les composants de Voix Entreprise qui sont trouvent sur les serveurs frontaux dans Skype pour Business Server, y compris le service de traduction et les divers composants de routage.
ms.openlocfilehash: eca9a83943d045c48b2b811e6370e54fc41f1714
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="front-end-server-voip-components-for-skype-for-business-server-2015"></a>Composants VoIP de serveur frontal pour Skype Entreprise Server 2015
 
Obtenir des informations sur les composants de Voix Entreprise qui sont trouvent sur les serveurs frontaux dans Skype pour Business Server, y compris le service de traduction et les divers composants de routage.
  
Les composants VoIP situés sur les serveurs frontaux sont les suivants :
  
- Service de conversion
    
- Composant de routage entrant
    
- Composant de routage sortant
    
- Composant de routage de messagerie unifiée Exchange
    
- Composant de routage InterCluster
    
- [Composant de serveur de médiation dans Skype pour Business Server 2015](mediation-server.md)
    
## <a name="translation-service"></a>Service de conversion

Le service de conversion est le composant serveur chargé de convertir un numéro composé au format E.164 ou autre format, selon les règles de normalisation définies par l’administrateur. Il est capable de convertir vers des formats autres qu’E.164 si votre organisation utilise un système de numérotation privé ou une passerelle, ou encore un système PBX qui ne prend pas en charge le format E.164.
  
## <a name="inbound-routing-component"></a>Composant de routage entrant

Le composant de routage de trafic entrant gère les appels entrants en grande partie en fonction des préférences spécifiées par les utilisateurs sur leurs clients de Voix Entreprise. Il permet également l’activation de la sonnerie sur le poste de délégués et de sonneries simultanées, si ces fonctionnalités sont configurées par l’utilisateur. Par exemple, les utilisateurs spécifient si les appels sans réponse doivent être transférés ou simplement consignés pour notification. Si le transfert d’appel est activé, les utilisateurs peuvent spécifier si les appels en attente doivent être transférés vers un autre numéro ou vers un serveur de messagerie unifiée Exchange a été configuré pour fournir la réponse aux appels. Le composant de routage de trafic entrant est installé par défaut sur tous les serveurs frontaux et serveur Standard Edition server. 
  
## <a name="outbound-routing-component"></a>Composant de routage sortant

Le composant de routage sortant achemine les appels vers des destinations PBX ou RTC. Il applique les règles d’autorisation d’appel, tel que défini par la stratégie de voix de l’utilisateur aux appelants et détermine la passerelle RTC optimale pour le routage de chaque appel. Le composant de routage sortant est installé par défaut sur tous les serveurs frontaux et serveur Standard Edition server.
  
La logique de routage qu’il utilise est en grande partie configurée par les administrateurs réseau ou de téléphonie en fonction des exigences de leur organisation. 
  
## <a name="exchange-um-routing-component"></a>Composant de routage de messagerie unifiée Exchange

Le composant de routage de messagerie unifiée Exchange gère le routage entre Skype pour Business Server et les serveurs qui exécutent Exchange messagerie unifiée (MU), pour intégrer Skype de Business Server avec les fonctionnalités de messagerie unifiée. 
  
Le composant de routage de messagerie unifiée Exchange gère également le reroutage des messages vocaux sur le RTPC si les serveurs de messagerie unifiée Exchange ne sont pas disponibles. Si vous avez des utilisateurs de Voix Entreprise à des sites de succursales qui n’ont pas de lien vers un site central, Survivable Branch Appliance que vous déployez sur le site de la succursale un WAN résilient fournit survivabilité de messagerie vocale pour les utilisateurs de la succursale suite à une panne de réseau étendue. Lors de la liaison réseau étendu n’est pas disponible, le programme Survivable Branch Appliance effectue les opérations suivantes :
  
- réachemine les appels sans réponse via la passerelle RTC vers le serveur de messagerie unifiée Exchange localisé sur le site central ;
    
- permet aux utilisateurs de récupérer leurs messages vocaux via la passerelle RTC ;
    
- met en file d’attente les notifications d’appels manqués, puis les télécharge vers le serveur de messagerie unifiée Exchange lorsque la liaison de réseau étendu est rétablie.
    
Pour activer la redirection de courrier vocal, nous recommandons de configurer Exchange UM Standard automatique (sa) pour accepter uniquement les messages votre administrateur Exchange.
  
Pour plus d’informations sur ces fonctionnalités, reportez-vous à la section [Sur site Exchange Unified intégration de la messagerie](http://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) et de [planification pour fiabilité de Voix Entreprise](http://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx), respectivement.
  
## <a name="intercluster-routing-component"></a>Composant de routage InterCluster

Le composant de routage Intercluster est responsable de l’acheminement d’appels au pool de Registre principal de l’appelé. Si qui n’est pas disponible, le composant route l’appel de pool de Registre de sauvegarde de l’appelé. Si les pools de Registrar principales et de sauvegarde de l’appelé sont inaccessibles sur le réseau IP, le composant de routage Intercluster redirige l’appel sur le réseau RTPC pour le numéro de téléphone de l’utilisateur.
  
## <a name="other-front-end-server-components-required-for-voip"></a>Autres composants du serveur frontal requis pour la voix sur IP (VoIP)

Autres composants résidant sur le serveur frontal ou directeur qui fournissent une prise en charge essentielle de la VoIP, mais qui ne sont pas eux-mêmes les composants VoIP, sont les suivants :
  
- **Services d’utilisateurs** : effectuent une recherche inversée de numéros sur le numéro de téléphone de destination de chaque appel entrant et associent ce numéro à l’URI SIP de l’utilisateur de destination. À l’aide de ces informations, le composant de routage de trafic entrant distribue l’appel à des points de terminaison SIP enregistrés de cet utilisateur. Services d’utilisateurs est un composant de base sur tous les serveurs frontaux et les directeurs.
    
- **Réplicateur d’utilisateurs** Extrait les numéros de téléphone des utilisateurs des Services de domaine Active Directory et les écrit dans les tables de la base de données RTC, où ils sont disponibles pour les Services de l’utilisateur et le serveur de carnet d’adresses. Le réplicateur d’utilisateurs est un composant de base sur tous les serveurs frontaux.
    
- **Serveur de carnet d’adresses** Fournit des informations de liste d’adresses globale des Services de domaine Active Directory à Skype pour les clients de serveur d’entreprise. Elle récupère également les informations utilisateur et de contact à partir de la base de données RTC, écrit les informations dans les fichiers de carnet d’adresses et stocke les fichiers dans un dossier partagé dans lequel ils sont téléchargés par Skype pour les clients de l’entreprise. Le serveur de carnet d’adresses écrit les informations dans la base de données RTCAb, qui est utilisé par le service de requête sur le Web adresse carnet à répondre aux requêtes de recherche d’utilisateurs de Skype pour les professionnels mobiles. Facultativement, il normalise numéros de téléphone utilisateur enterprise qui sont écrites dans la base de données RTC en vue de la mise en service des contacts de l’utilisateur dans Skype pour les entreprises. Le service de carnet d’adresses est installé par défaut sur tous les serveurs frontaux. Le service de requête sur le Web adresse livre est installé par défaut avec les services Web sur chaque serveurs frontaux.
    

