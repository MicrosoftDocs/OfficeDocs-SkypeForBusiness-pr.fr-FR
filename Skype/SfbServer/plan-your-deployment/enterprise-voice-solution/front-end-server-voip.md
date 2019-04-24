---
title: Composants VoIP du serveur frontal pour Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: Découvrez les composants d’Enterprise Voice qui sont trouvent sur les serveurs frontaux dans Skype pour Business Server, y compris les différents composants de routage et de service de traduction automatique.
ms.openlocfilehash: caeec86f4b4a965570773ee4bc51a4e752e76e46
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206879"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>Composants VoIP du serveur frontal pour Skype pour Business Server

Découvrez les composants d’Enterprise Voice qui sont trouvent sur les serveurs frontaux dans Skype pour Business Server, y compris les différents composants de routage et de service de traduction automatique.

Les composants VoIP situés sur les serveurs frontaux sont comme suit :

- Service de conversion

- Composant de routage entrant

- Composant de routage sortant

- Composant de routage de messagerie unifiée Exchange

- Composant de routage InterCluster

- [Composant serveur de médiation dans Skype pour Business Server](mediation-server.md)

## <a name="translation-service"></a>Service de conversion

Le service de conversion est le composant serveur chargé de convertir un numéro composé au format E.164 ou autre format, selon les règles de normalisation définies par l’administrateur. Il est capable de convertir vers des formats autres qu’E.164 si votre organisation utilise un système de numérotation privé ou une passerelle, ou encore un système PBX qui ne prend pas en charge le format E.164.

## <a name="inbound-routing-component"></a>Composant de routage entrant

Le composant de routage entrant gère les appels entrants en grande partie selon des préférences sont spécifiés par les utilisateurs sur leurs clients Enterprise Voice. Il permet également l’activation de la sonnerie sur le poste de délégués et de sonneries simultanées, si ces fonctionnalités sont configurées par l’utilisateur. Par exemple, les utilisateurs spécifient si les appels sans réponse doivent être transférés ou simplement consignés pour notification. Si le transfert d’appel est activé, les utilisateurs peuvent spécifier si les appels sans réponse doivent être transférés vers un autre numéro ou vers un serveur de messagerie unifiée Exchange qui a été configuré pour fournir la réponse aux appels. Le composant de routage entrant est installé par défaut sur tous les serveurs Standard Edition et les serveurs frontaux.

## <a name="outbound-routing-component"></a>Composant de routage sortant

Le composant de routage sortant achemine les appels vers des destinations PBX ou RTC. Elle applique les règles d’autorisation d’appel, tel que défini par la stratégie de voix de l’utilisateur, aux appelants et détermine la passerelle PSTN optimale pour acheminer chaque appel. Le composant de routage sortant est installé par défaut sur tous les serveurs Standard Edition et les serveurs frontaux.

La logique de routage qu’il utilise est en grande partie configurée par les administrateurs réseau ou de téléphonie en fonction des exigences de leur organisation.

## <a name="exchange-um-routing-component"></a>Composant de routage de messagerie unifiée Exchange

Le composant de routage de messagerie unifiée Exchange gère le routage entre Skype pour Business Server et les serveurs qui exécutent Exchange messagerie unifiée (MU), afin d’intégrer Skype pour Business Server aux fonctionnalités de messagerie unifiée.

Le composant de routage de messagerie unifiée Exchange gère également le réacheminement de la messagerie vocale via la passerelle PSTN si les serveurs de messagerie unifiée Exchange ne sont pas disponibles. Si vous avez des utilisateurs Enterprise Voice sur les sites de succursale qui n’ont pas de lien vers un site central, Survivable Branch Appliance que vous déployez sur le site de succursale un WAN résistant fournit survivabilité de la messagerie vocale pour les utilisateurs de succursale pendant une panne de réseau étendue. Lors de la liaison WAN n’est pas disponible, le Survivable Branch Appliance effectue les opérations suivantes :

- réachemine les appels sans réponse via la passerelle RTC vers le serveur de messagerie unifiée Exchange localisé sur le site central ;

- permet aux utilisateurs de récupérer leurs messages vocaux via la passerelle RTC ;

- met en file d’attente les notifications d’appels manqués, puis les télécharge vers le serveur de messagerie unifiée Exchange lorsque la liaison de réseau étendu est rétablie.

Pour permettre le réacheminement des messages vocaux, nous recommandons que votre administrateur Exchange configurer Exchange UM automatique standard pour accepter uniquement les messages.

Pour plus d’informations sur ces fonctionnalités, reportez-vous aux rubriques [On-Premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) et [Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx), respectivement.

## <a name="intercluster-routing-component"></a>Composant de routage InterCluster

Le composant de routage Intercluster est chargé de routage des appels à un pool de serveurs d’inscriptions principal de l’appelé. Si qui n’est pas disponible, le composant achemine l’appel vers le pool de serveurs d’inscriptions de sauvegarde de l’appelé. Si les pools de serveurs d’inscriptions principales et secondaire de l’appelé sont inaccessibles sur le réseau IP, le composant de routage Intercluster redirige l’appel via la passerelle PSTN au numéro de téléphone de l’utilisateur.

## <a name="other-front-end-server-components-required-for-voip"></a>Autres composants du serveur frontal requis pour la voix sur IP (VoIP)

Les autres composants installé sur le serveur frontal ou le directeur qui fournissent la prise en charge essentielle pour VoIP, sans être eux-mêmes des composants VoIP, sont les suivantes :

- **Services d’utilisateurs** : effectuent une recherche inversée de numéros sur le numéro de téléphone de destination de chaque appel entrant et associent ce numéro à l’URI SIP de l’utilisateur de destination. À l’aide de ces informations, le composant de routage entrant dirige l’appel à des systèmes d’extrémité SIP enregistrés de cet utilisateur. Services d’utilisateurs est un composant essentiel de tous les serveurs frontaux et les directeurs.

- **Réplicateur d’utilisateurs** Extrait les numéros de téléphone des Services de domaine Active Directory et les écrit dans les tables de la base de données RTC, où ils sont disponibles pour les Services de l’utilisateur et le serveur de carnet d’adresses. Le réplicateur d’utilisateurs est un composant essentiel de tous les serveurs frontaux.

- **Serveur de carnet d’adresses** Fournit des informations de liste d’adresses globale des Services de domaine Active Directory à Skype pour les clients Business Server. Elle récupère également les informations utilisateur et de contact à partir de la base de données RTC, écrit les informations sur les fichiers de carnet d’adresses, puis stocke les fichiers sur un dossier partagé dans lequel ils sont téléchargés par Skype pour les clients d’entreprise. Le serveur de carnet d’adresses écrit les informations dans la base de données RTCAb, qui est utilisé par le service de requête sur le Web téléchargeable adresse à répondre aux requêtes de recherche utilisateur de Skype pour les entreprises mobiles. Si vous le souhaitez, il normalise entreprise les numéros de téléphone qui sont écrites dans la base de données RTC pour les besoins de mise en service des contacts utilisateur dans Skype pour les entreprises. Le service de carnet d’adresses est installé par défaut sur tous les serveurs frontaux. Le service de requête sur le Web téléchargeable adresse est installé par défaut avec les services Web sur chaque serveurs frontaux.


