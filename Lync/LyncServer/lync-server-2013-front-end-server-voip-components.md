---
title: 'Lync Server 2013 : composants VoIP du serveur frontal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bab5751fc0291047f3795731f379d1e14f5f12b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739734"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-server-voip-components-for-lync-server-2013"></a>Composants VoIP du serveur frontal pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Les composants VoIP situés sur les serveurs frontaux sont les suivants :

  - Service de conversion

  - Composant de routage entrant

  - Composant de routage sortant

  - Composant de routage de messagerie unifiée Exchange

  - Composant de routage InterCluster

  - [Composant serveur de médiation dans Lync Server 2013](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a>Service de conversion

Le service de conversion est le composant serveur chargé de convertir un numéro composé au format E.164 ou autre format, selon les règles de normalisation définies par l’administrateur. Il est capable de convertir vers des formats autres qu’E.164 si votre organisation utilise un système de numérotation privé ou une passerelle, ou encore un système PBX qui ne prend pas en charge le format E.164.

</div>

<div>

## <a name="inbound-routing-component"></a>Composant de routage entrant

Le composant de routage entrant gère les appels entrants en fonction des préférences spécifiées par les utilisateurs sur leurs clients vocaux d’entreprise. Il permet également l’activation de la sonnerie sur le poste de délégués et de sonneries simultanées, si ces fonctionnalités sont configurées par l’utilisateur. Par exemple, les utilisateurs spécifient si les appels sans réponse doivent être transférés ou simplement consignés pour notification. Si le transfert d’appel est activé, les utilisateurs peuvent spécifier si les appels sans réponse doivent être transférés vers un autre numéro ou vers un serveur de messagerie unifiée configuré pour fournir les réponses aux appels. Le composant de routage de trafic entrant est installé par défaut sur tous les serveurs frontaux et serveur Standard Edition.

</div>

<div>

## <a name="outbound-routing-component"></a>Composant de routage sortant

Le composant de routage sortant achemine les appels vers des destinations PBX ou RTC. Il applique aux appelants des règles d’autorisation d’appels issues de la stratégie de voix de l’utilisateur et détermine la meilleure passerelle RTC pour le routage de chaque appel. Le composant de routage sortant est installé par défaut sur tous les serveurs frontaux et serveur Standard Edition.

La logique de routage qu’il utilise est en grande partie configurée par les administrateurs réseau ou de téléphonie en fonction des exigences de leur organisation.

</div>

<div>

## <a name="exchange-um-routing-component"></a>Composant de routage de messagerie unifiée Exchange

Le composant routage de messagerie unifiée Exchange gère le routage entre le serveur Lync et les serveurs exécutant la messagerie unifiée Exchange, pour intégrer Lync Server aux fonctionnalités de messagerie unifiée.

Le composant routage de messagerie UNIFIÉe Exchange gère également le reroutage de la messagerie vocale sur le RTC si des serveurs de messagerie unifiée Exchange ne sont pas disponibles. Si vous avez des utilisateurs d’Enterprise Voice sur des sites de succursale qui n’ont pas de lien réseau étendu fiable vers un site central, l’unité de branchement survivant que vous déployez sur le site de succursale fournit une survie de la messagerie vocale pour les utilisateurs de succursales en cas de panne du réseau étendu. Lorsque le lien WAN n’est pas disponible, l’unité de branchement Survivable effectue les actions suivantes :

  - réachemine les appels sans réponse via la passerelle RTC vers le serveur de messagerie unifiée Exchange localisé sur le site central ;

  - permet aux utilisateurs de récupérer leurs messages vocaux via la passerelle RTC ;

  - met en file d’attente les notifications d’appels manqués, puis les télécharge vers le serveur de messagerie unifiée Exchange lorsque la liaison de réseau étendu est rétablie.

Pour activer le reroutage de la messagerie vocale, nous vous conseillons de configurer le standard automatique de votre administrateur Exchange pour qu’il accepte uniquement les messages.

Pour plus d’informations sur ces fonctionnalités, reportez-vous à la rubrique [planification de l’intégration de la messagerie unifiée Exchange dans Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) et [planification de la résilience vocale entreprise dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectivement.

</div>

<div>

## <a name="intercluster-routing-component"></a>Composant de routage InterCluster

Le composant de routage Intercluster est chargé d’acheminer les appels vers le pool de serveurs d’inscriptions principal du destinataire de l’appel. S’il n’est pas disponible, le composant achemine l’appel vers le pool d’inscriptions secondaire du destinataire de l’appel. Si ces deux pools ne sont pas joignables via le réseau IP, le composant de routage Intercluster réachemine l’appel vers le numéro de téléphone de l’utilisateur via la passerelle RTC.

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a>Autres composants du serveur frontal requis pour la voix sur IP (VoIP)

D’autres composants résidant sur le serveur frontal ou le directeur qui fournissent une prise en charge essentielle de VoIP, mais qui ne sont pas eux-mêmes des composants VoIP, incluent les éléments suivants :

  - **Services d’utilisateurs** : effectuent une recherche inversée de numéros sur le numéro de téléphone de destination de chaque appel entrant et associent ce numéro à l’URI SIP de l’utilisateur de destination. À l’aide de ces informations, le composant de routage entrant dirige l’appel vers les points de terminaison SIP enregistrés de cet utilisateur. User Services est un composant principal de tous les serveurs et directeurs frontaux.

  - **Réplicateur d’utilisateurs** Extrait les numéros de téléphone des utilisateurs des services de domaine Active Directory et les écrit dans les tables de la base de données RTC qui sont accessibles aux services d’utilisateurs et au serveur du carnet d’adresses. Le réplicateur d’utilisateurs est un composant principal sur tous les serveurs frontaux.

  - **Serveur de carnet d’adresses** Fournit des informations de liste d’adresses globale provenant des services de domaine Active Directory aux clients Lync Server. Elle récupère également les informations d’utilisateur et de contact de la base de données RTC, enregistre les informations dans les fichiers du carnet d’adresses, puis stocke les fichiers dans un dossier partagé dans lequel ils sont téléchargés par les clients Lync. Le serveur du carnet d’adresses écrit les informations dans la base de données RTCAb, qui est utilisée par le service de requête sur le carnet d’adresses pour répondre aux requêtes de recherche utilisateur de Microsoft Lync 2010 mobile. Il est également normalisé de mettre en place les numéros de téléphone des utilisateurs d’entreprise qui sont écrits dans la base de données RTC dans le cadre de la mise en service des contacts utilisateur dans Lync. Le service de carnet d’adresses est installé par défaut sur tous les serveurs frontaux. Le service de requête sur le carnet d’adresses est installé par défaut avec les services Web sur chaque serveur frontal.

</div>

</div>

<span> </span>

</div>

</div>

</div>

