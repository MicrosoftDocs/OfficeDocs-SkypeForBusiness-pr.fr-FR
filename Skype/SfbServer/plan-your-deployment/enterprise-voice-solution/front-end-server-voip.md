---
title: Composants VoIP du serveur frontal pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: En savoir plus sur les composants vocaux d’entreprise situés sur des serveurs frontaux dans Skype entreprise Server, y compris le service de traduction et divers composants de routage.
ms.openlocfilehash: eae2f389720a6c359f442a7a163d5b4b5aef6e26
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802964"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>Composants VoIP du serveur frontal pour Skype entreprise Server

En savoir plus sur les composants vocaux d’entreprise situés sur des serveurs frontaux dans Skype entreprise Server, y compris le service de traduction et divers composants de routage.

Les composants VoIP situés sur les serveurs frontaux sont les suivants :

- Service de conversion

- Composant de routage entrant

- Composant de routage sortant

- Composant de routage de messagerie unifiée Exchange

- Composant de routage InterCluster

- [Composant serveur de médiation dans Skype entreprise Server](mediation-server.md)

## <a name="translation-service"></a>Service de conversion

Le service de conversion est le composant serveur chargé de convertir un numéro composé au format E.164 ou autre format, selon les règles de normalisation définies par l’administrateur. Il est capable de convertir vers des formats autres qu’E.164 si votre organisation utilise un système de numérotation privé ou une passerelle, ou encore un système PBX qui ne prend pas en charge le format E.164.

## <a name="inbound-routing-component"></a>Composant de routage entrant

Le composant de routage entrant gère les appels entrants en fonction des préférences spécifiées par les utilisateurs sur leurs clients vocaux d’entreprise. Il permet également l’activation de la sonnerie sur le poste de délégués et de sonneries simultanées, si ces fonctionnalités sont configurées par l’utilisateur. Par exemple, les utilisateurs spécifient si les appels sans réponse doivent être transférés ou simplement consignés pour notification. Si le transfert d’appel est activé, les utilisateurs peuvent spécifier si les appels sans réponse doivent être transférés vers un autre numéro ou vers un serveur de messagerie unifiée configuré pour fournir les réponses aux appels. Le composant de routage de trafic entrant est installé par défaut sur tous les serveurs frontaux et serveur Standard Edition.

## <a name="outbound-routing-component"></a>Composant de routage sortant

Le composant de routage sortant achemine les appels vers des destinations PBX ou RTC. Il applique des règles d’autorisation d’appel, telles qu’elles sont définies par la stratégie vocale de l’utilisateur, aux appelants et détermine la passerelle RTC optimale pour le routage de chaque appel. Le composant de routage sortant est installé par défaut sur tous les serveurs frontaux et serveur Standard Edition.

La logique de routage qu’il utilise est en grande partie configurée par les administrateurs réseau ou de téléphonie en fonction des exigences de leur organisation.

## <a name="exchange-um-routing-component"></a>Composant de routage de messagerie unifiée Exchange

Le composant routage de messagerie unifiée Exchange gère le routage entre Skype entreprise Server et les serveurs exécutant la messagerie unifiée Exchange, pour intégrer Skype entreprise Server aux fonctionnalités de messagerie unifiée.

Le composant routage de messagerie UNIFIÉe Exchange gère également le reroutage de la messagerie vocale sur le RTC si des serveurs de messagerie unifiée Exchange ne sont pas disponibles. Si vous avez des utilisateurs d’Enterprise Voice sur des sites de succursale qui n’ont pas de lien réseau étendu fiable vers un site central, l’unité de branchement survivant que vous déployez sur le site de succursale fournit une survie de la messagerie vocale pour les utilisateurs de succursales en cas de panne du réseau étendu. Lorsque le lien WAN n’est pas disponible, l’unité de branchement Survivable effectue les actions suivantes :

- réachemine les appels sans réponse via la passerelle RTC vers le serveur de messagerie unifiée Exchange localisé sur le site central ;

- permet aux utilisateurs de récupérer leurs messages vocaux via la passerelle RTC ;

- met en file d’attente les notifications d’appels manqués, puis les télécharge vers le serveur de messagerie unifiée Exchange lorsque la liaison de réseau étendu est rétablie.

Pour activer le reroutage de la messagerie vocale, nous vous conseillons de configurer le standard automatique de votre administrateur Exchange pour qu’il accepte uniquement les messages.

Pour plus d’informations sur ces fonctionnalités, reportez-vous aux rubriques [On-Premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) et [Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx), respectivement.

## <a name="intercluster-routing-component"></a>Composant de routage InterCluster

Le composant de routage Intercluster est responsable du routage des appels vers le pool d’inscriptions principal de l’appelant. Si ce n’est pas le cas, le composant route l’appel vers le pool d’registraire de sauvegarde de l’appelant. Si les pools d’inscriptions principales et de sauvegarde de l’appelant ne sont pas accessibles sur le réseau IP, le composant de routage d’interclusters réachemine l’appel sur le RTC vers le numéro de téléphone de l’utilisateur.

## <a name="other-front-end-server-components-required-for-voip"></a>Autres composants du serveur frontal requis pour la voix sur IP (VoIP)

D’autres composants résidant sur le serveur frontal ou le directeur qui fournissent une prise en charge essentielle de VoIP, mais qui ne sont pas eux-mêmes des composants VoIP, incluent les éléments suivants :

- **Services d’utilisateurs** : effectuent une recherche inversée de numéros sur le numéro de téléphone de destination de chaque appel entrant et associent ce numéro à l’URI SIP de l’utilisateur de destination. À l’aide de ces informations, le composant de routage entrant distribue l’appel aux points de terminaison SIP inscrits de l’utilisateur. User Services est un composant principal de tous les serveurs et directeurs frontaux.

- **Réplicateur d’utilisateurs** Extrait les numéros de téléphone des utilisateurs des services de domaine Active Directory et les écrit dans les tables de la base de données RTC qui sont accessibles aux services d’utilisateurs et au serveur du carnet d’adresses. Le réplicateur d’utilisateurs est un composant principal sur tous les serveurs frontaux.

- **Serveur de carnet d’adresses** Fournit des informations de liste d’adresses globale provenant des services de domaine Active Directory aux clients Skype entreprise Server. Elle récupère également les informations d’utilisateur et de contact de la base de données RTC, enregistre les informations dans les fichiers du carnet d’adresses, puis stocke les fichiers dans un dossier partagé dans lequel ils sont téléchargés par les clients Skype entreprise. Le serveur du carnet d’adresses écrit les informations dans la base de données RTCAb, qui est utilisée par le service de requête sur le carnet d’adresses pour répondre aux requêtes de recherche de l’utilisateur de Skype entreprise mobile. Il est également possible de faire figurer les numéros de téléphone des utilisateurs d’entreprise qui sont écrits dans la base de données RTC dans le cadre de la mise en service des contacts de l’utilisateur dans Skype entreprise. Le service de carnet d’adresses est installé par défaut sur tous les serveurs frontaux. Le service de requête sur le carnet d’adresses est installé par défaut avec les services Web sur chaque serveur frontal.


