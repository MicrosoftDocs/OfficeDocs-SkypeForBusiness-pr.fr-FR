---
title: Composants VoIP du serveur frontal pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: Découvrez les composants Voix Entreprise qui se trouvent sur les serveurs frontaux dans Skype Entreprise Server, y compris le service de traduction et divers composants de routage.
ms.openlocfilehash: d649185ccc83da925cc7341087d373d67523b5b6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850727"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>Composants VoIP du serveur frontal pour Skype Entreprise Server

Découvrez les composants Voix Entreprise qui se trouvent sur les serveurs frontaux dans Skype Entreprise Server, y compris le service de traduction et divers composants de routage.

Les composants VoIP situés sur les serveurs frontaux sont les suivants :

- Service de traduction

- Composant de routage entrant

- Composant de routage sortant

- Composant de routage de messagerie unifiée Exchange

- Composant de routage InterCluster

- [Composant serveur de médiation dans Skype Entreprise Server](mediation-server.md)

## <a name="translation-service"></a>Service de traduction

Le service de traduction est le composant serveur chargé de convertir un numéro composé au format E.164 ou autre format, selon les règles de normalisation définies par l’administrateur. Il est capable de traduire vers des formats autres qu’E.164 si votre organisation utilise un système de numérotation privé ou une passerelle, ou encore un système PBX qui ne prend pas en charge le format E.164.

## <a name="inbound-routing-component"></a>Composant de routage entrant

Le composant de routage entrant gère essentiellement les appels entrants selon les préférences que les utilisateurs ont spécifiées sur leurs clients Enterprise Voice. Il permet également l’activation de la sonnerie sur le poste de délégués et de sonneries simultanées, si ces fonctionnalités sont configurées par l’utilisateur. Par exemple, les utilisateurs spécifient si les appels sans réponse doivent être transférés ou simplement consignés pour notification. Si le forwarding d’appel est activé, les utilisateurs peuvent spécifier si les appels sans réponse doivent être transmis à un autre numéro ou à un serveur de messagerie un Exchange qui a été configuré pour fournir des réponses aux appels. Le composant de routage entrant est installé par défaut sur tous les serveurs Édition Standard serveur frontal et frontal.

## <a name="outbound-routing-component"></a>Composant de routage sortant

Le composant de routage sortant achemine les appels vers des destinations PBX ou PSTN. Il applique des règles d’autorisation d’appel, telles que définies par la stratégie de voix de l’utilisateur, aux appelants et détermine la passerelle PSTN optimale pour le routage de chaque appel. Le composant de routage sortant est installé par défaut sur tous les serveurs Édition Standard serveurs frontux.

La logique de routage qu’il utilise est en grande partie configurée par les administrateurs réseau ou de téléphonie en fonction des exigences de leur organisation.

## <a name="exchange-um-routing-component"></a>Composant de routage de messagerie unifiée Exchange

Le Exchange de routage de messagerie unifiée gère le routage entre Skype Entreprise Server et les serveurs exécutant la messagerie unifiée Exchange afin d’intégrer les Skype Entreprise Server aux fonctionnalités de messagerie unifiée.

Le Exchange de routage de messagerie unie gère également le réroutage de la messagerie vocale sur le réseau R EXCHANGE si les serveurs de messagerie un Exchange sont indisponibles. Si vous avez des utilisateurs Voix Entreprise sur les sites de succursale qui ne disposent pas d’une liaison de réseau wan résiliente vers un site central, le Survivable Branch Appliance que vous déployez sur le site de succursale offre une survivabilité de messagerie vocale pour les utilisateurs de succursale lors d’une panne de réseau wan. Lorsque la liaison WAN est indisponible, l'appareil Survivable Branch Appliance procède comme suit :

- réachemine les appels sans réponse via la passerelle PSTN vers le serveur de messagerie unifiée Exchange localisé sur le site central ;

- permet aux utilisateurs de récupérer leurs messages vocaux via la passerelle PSTN ;

- met en file d’attente les notifications d’appels manqués, puis les télécharge vers le serveur de messagerie unifiée Exchange lorsque la liaison de réseau étendu est rétablie.

Pour activer le réaroutage de la messagerie vocale, il est recommandé que votre administrateur Exchange configure Exchange messagerie un Standard automatique (AA) pour accepter uniquement les messages.

Pour plus d’informations sur ces fonctionnalités, voir  [On-Premises Exchange Unified Messaging Integration](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration) and [Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency), respectivement.

## <a name="intercluster-routing-component"></a>Composant de routage InterCluster

Le composant de routage Intercluster est responsable du routage des appels vers le pool de bureaux d’inscriptions principal de l’appelé. S’il n’est pas disponible, le composant approvisionnement l’appel vers le pool de sauvegarde de l’appelé. Si les pools de bureaux d’inscriptions principal et de sauvegarde de l’appelé sont inaccessibles sur le réseau IP, le composant de routage Intercluster redirige l’appel sur le réseau téléphonique PSTN vers le numéro de téléphone de l’utilisateur.

## <a name="other-front-end-server-components-required-for-voip"></a>Autres composants du serveur frontal requis pour la voix sur IP (VoIP)

Les autres composants résidant sur le serveur frontal ou le directeur qui fournissent une prise en charge essentielle pour VoIP, mais qui ne sont pas eux-mêmes des composants VoIP, sont les suivants :

- **Services d’utilisateurs** : effectuent une recherche inversée de numéros sur le numéro de téléphone de destination de chaque appel entrant et associent ce numéro à l’URI SIP de l’utilisateur de destination. À l’aide de ces informations, le composant de routage entrant distribue l’appel aux points de terminaison SIP enregistrés de cet utilisateur. Les services d’utilisateurs sont un composant essentiel sur tous les serveurs frontaux et directeurs.

- **Réplicateur d’utilisateurs** Extrait les numéros de téléphone des services de domaine Active Directory et les écrit dans des tables de la base de données RTC, où ils sont disponibles pour les services d’utilisateurs et le serveur de carnet d’adresses. Le réplicateur d’utilisateurs est un composant principal sur tous les serveurs frontux.

- **Serveur de carnet d’adresses** Fournit des informations de liste d’adresses globale des services de domaine Active Directory Skype Entreprise Server clients. Il récupère également les informations d’utilisateur et de contact de la base de données RTC, écrit les informations dans les fichiers de carnet d’adresses, puis stocke les fichiers dans un dossier partagé où ils sont téléchargés par les clients Skype Entreprise. Le serveur de carnet d’adresses écrit les informations dans la base de données RTCAb, qui est utilisée par le service de requête Web du carnet d’adresses pour répondre aux requêtes de recherche des utilisateurs à partir Skype Entreprise mobile. Elle normalise éventuellement les numéros de téléphone des utilisateurs d’entreprise écrits dans la base de données RTC dans le but de mettre en service les contacts des utilisateurs dans Skype Entreprise. Le service de carnet d’adresses est installé par défaut sur tous les serveurs frontux. Le service de requête Web du carnet d’adresses est installé par défaut avec les services Web sur chaque serveur frontal.