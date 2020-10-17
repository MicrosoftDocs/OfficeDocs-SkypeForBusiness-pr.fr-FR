---
title: 'Lync Server 2013 : composants VoIP de serveur frontal'
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
ms.openlocfilehash: 62261a4d4651e38941f5068b58636b82d0151965
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500701"
---
# <a name="front-end-server-voip-components-for-lync-server-2013"></a>Composants VoIP de serveur frontal pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Les composants VoIP situés sur les serveurs frontaux sont les suivants :

  - Service de traduction

  - Composant de routage entrant

  - Composant de routage sortant

  - Composant de routage de messagerie unifiée Exchange

  - Composant de routage InterCluster

  - [Composant de serveur de médiation dans Lync Server 2013](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a>Service de traduction

Le service de traduction est le composant serveur chargé de convertir un numéro composé au format E.164 ou autre format, selon les règles de normalisation définies par l’administrateur. Il est capable de traduire vers des formats autres qu’E.164 si votre organisation utilise un système de numérotation privé ou une passerelle, ou encore un système PBX qui ne prend pas en charge le format E.164.

</div>

<div>

## <a name="inbound-routing-component"></a>Composant de routage entrant

Le composant de routage entrant gère essentiellement les appels entrants selon les préférences que les utilisateurs ont spécifiées sur leurs clients Enterprise Voice. Il permet également l’activation de la sonnerie sur le poste de délégués et de sonneries simultanées, si ces fonctionnalités sont configurées par l’utilisateur. Par exemple, les utilisateurs spécifient si les appels sans réponse doivent être transférés ou simplement consignés pour notification. Si le transfert d’appel est activé, les utilisateurs peuvent spécifier si les appels sans réponse doivent être transférés vers un autre numéro ou vers un serveur de messagerie unifiée Exchange configuré pour fournir le répondeur automatique. Le composant de routage entrant est installé par défaut sur tous les serveurs Standard Edition et serveurs frontaux.

</div>

<div>

## <a name="outbound-routing-component"></a>Composant de routage sortant

Le composant de routage sortant achemine les appels vers des destinations PBX ou PSTN. Il applique aux appelants des règles d’autorisation d’appels issues de la stratégie de voix de l’utilisateur et détermine la meilleure passerelle PSTN pour le routage de chaque appel. Le composant de routage sortant est installé par défaut sur tous les serveurs Standard Edition et serveurs frontaux.

La logique de routage qu’il utilise est en grande partie configurée par les administrateurs réseau ou de téléphonie en fonction des exigences de leur organisation.

</div>

<div>

## <a name="exchange-um-routing-component"></a>Composant de routage de messagerie unifiée Exchange

Le composant de routage de messagerie unifiée Exchange gère le routage entre Lync Server et les serveurs exécutant la messagerie unifiée Exchange, pour intégrer Lync Server aux fonctionnalités de messagerie unifiée.

Le composant de routage de messagerie unifiée Exchange gère également le réacheminement de la messagerie vocale sur le réseau téléphonique commuté si les serveurs de messagerie unifiée Exchange sont indisponibles. Si vous avez des utilisateurs de voix entreprise sur des sites de succursale qui n’ont pas de liaison de réseau étendu résiliente à un site central, le Survivable Branch Appliance que vous déployez sur le site de succursale offre une survivabilité de la messagerie vocale pour les utilisateurs de succursale lors d’une panne de réseau étendu. Lorsque la liaison WAN est indisponible, l'appareil Survivable Branch Appliance procède comme suit :

  - réachemine les appels sans réponse via la passerelle PSTN vers le serveur de messagerie unifiée Exchange localisé sur le site central ;

  - permet aux utilisateurs de récupérer leurs messages vocaux via la passerelle PSTN ;

  - met en file d’attente les notifications d’appels manqués, puis les télécharge vers le serveur de messagerie unifiée Exchange lorsque la liaison de réseau étendu est rétablie.

Pour activer le reroutage de la messagerie vocale, il est recommandé que votre administrateur Exchange configurez le standard automatique de messagerie unifiée Exchange (AA) pour accepter uniquement les messages.

Pour plus d’informations sur ces fonctionnalités, reportez-vous à la rubrique [Planning for Exchange Unified Messaging Integration in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) et [Planning for Enterprise Voice Resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectivement.

</div>

<div>

## <a name="intercluster-routing-component"></a>Composant de routage InterCluster

Le composant de routage Intercluster est chargé d’acheminer les appels vers le pool de serveurs d’inscriptions principal du destinataire de l’appel. S’il n’est pas disponible, le composant achemine l’appel vers le pool d’inscriptions secondaire du destinataire de l’appel. Si ces deux pools ne sont pas joignables via le réseau IP, le composant de routage Intercluster réachemine l’appel vers le numéro de téléphone de l’utilisateur via la passerelle PSTN.

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a>Autres composants du serveur frontal requis pour la voix sur IP (VoIP)

Les autres composants qui résident sur le serveur frontal ou le directeur qui fournissent la prise en charge essentielle de VoIP, mais qui ne sont pas eux-mêmes des composants VoIP, incluent les éléments suivants :

  - **Services d’utilisateurs** : effectuent une recherche inversée de numéros sur le numéro de téléphone de destination de chaque appel entrant et associent ce numéro à l’URI SIP de l’utilisateur de destination. À l’aide de ces informations, le composant de routage entrant dirige l’appel vers les points de terminaison SIP enregistrés de cet utilisateur. Services d’utilisateurs est un composant de base sur tous les serveurs frontaux et les directeurs.

  - **Réplicateur d’utilisateurs** Extrait les numéros de téléphone des utilisateurs des services de domaine Active Directory et les écrit dans les tables de la base de données RTC, où ils sont disponibles pour les services d’utilisateurs et le serveur de carnet d’adresses. Le réplicateur d’utilisateurs est un composant principal sur tous les serveurs frontaux.

  - **Serveur de carnet d’adresses** Fournit des informations sur les listes d’adresses globales des services de domaine Active Directory aux clients Lync Server. Il récupère également les informations d’utilisateur et de contact de la base de données RTC, écrit les informations dans les fichiers du carnet d’adresses, puis stocke les fichiers dans un dossier partagé dans lequel ils sont téléchargés par les clients Lync. Le serveur de carnet d’adresses écrit les informations dans la base de données RTCAb, qui est utilisée par le service de requête Web du carnet d’adresses pour répondre aux requêtes de recherche utilisateur à partir de Microsoft Lync 2010 mobile. Elle normalise éventuellement les numéros de téléphone des utilisateurs de l’entreprise qui sont écrits dans la base de données RTC à des fins de mise en service des contacts utilisateur dans Lync. Le service de carnet d’adresses est installé par défaut sur tous les serveurs frontaux. Le service de requête Web du carnet d’adresses est installé par défaut avec les services Web sur chaque serveur frontal.

</div>

</div>

<span> </span>

</div>

</div>

</div>

