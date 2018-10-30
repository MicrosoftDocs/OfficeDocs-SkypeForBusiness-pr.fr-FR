---
title: 'Lync Server 2013 : Composants VoIP de serveur frontal'
TOCTitle: Composants VoIP de serveur frontal
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425812(v=OCS.15)
ms:contentKeyID: 49296782
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Composants VoIP de serveur frontal pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-01_

Les composants VoIP situés sur les serveurs frontaux sont les suivants :

  - Service de conversion

  - Composant de routage entrant

  - Composant de routage sortant

  - Composant de routage de messagerie unifiée Exchange

  - Composant de routage InterCluster

  - [Composant Serveur de médiation dans Lync Server 2013](lync-server-2013-mediation-server-component.md)

## Service de conversion

Le service de conversion est le composant serveur chargé de convertir un numéro composé au format E.164 ou autre format, selon les règles de normalisation définies par l’administrateur. Il est capable de convertir vers des formats autres qu’E.164 si votre organisation utilise un système de numérotation privé ou une passerelle, ou encore un système PBX qui ne prend pas en charge le format E.164.

## Composant de routage entrant

Le composant de routage entrant gère les appels entrants en grande partie selon des préférences indiquées par les utilisateurs sur leurs clients Voix Entreprise. Il permet également l’activation de la sonnerie sur le poste de délégués et de sonneries simultanées, si ces fonctionnalités sont configurées par l’utilisateur. Par exemple, les utilisateurs spécifient si les appels sans réponse doivent être transférés ou simplement consignés pour notification. Si le transfert d’appel est activé, les utilisateurs peuvent spécifier si les appels sans réponse doivent être transférés vers un autre numéro ou vers un serveur de messagerie unifiée Exchange configuré pour répondre aux appels. Le composant de routage entrant est installé par défaut sur tout serveur Standard Edition et les serveurs frontaux.

## Composant de routage sortant

Le composant de routage sortant achemine les appels vers des destinations PBX ou RTC. Il applique aux appelants des règles d’autorisation d’appels issues de la stratégie de voix de l’utilisateur et détermine la meilleure passerelle RTC pour le routage de chaque appel. Le composant de routage sortant est installé par défaut sur tout serveur Standard Edition et les serveurs frontaux.

La logique de routage qu’il utilise est en grande partie configurée par les administrateurs réseau ou de téléphonie en fonction des exigences de leur organisation.

## Composant de routage de messagerie unifiée Exchange

Le composant de routage de messagerie unifiée Exchange gère le routage entre Lync Server et des serveurs qui exécutent la messagerie unifiée Exchange afin d’intégrer Lync Server aux fonctionnalités de messagerie unifiée.

Le composant de routage de messagerie unifiée Exchange gère également le réacheminement de la messagerie vocale via la passerelle RTC en cas d’indisponibilité des serveurs de messagerie unifiée Exchange. Si certains utilisateurs de Voix Entreprise se trouvant sur un site de succursale ne disposent pas d’une liaison de réseau étendu (WAN) résistante vers le site central, le Survivable Branch Appliance que vous déployez sur le site de succursale peut assurer la survivabilité des messages vocaux en cas de panne du réseau étendu. Lorsque la liaison de réseau étendu est indisponible, le Survivable Branch Appliance effectue ce qui suit :

  - réachemine les appels sans réponse via la passerelle RTC vers le serveur de messagerie unifiée Exchange localisé sur le site central ;

  - permet aux utilisateurs de récupérer leurs messages vocaux via la passerelle RTC ;

  - met en file d’attente les notifications d’appels manqués, puis les télécharge vers le serveur de messagerie unifiée Exchange lorsque la liaison de réseau étendu est rétablie.

Pour permettre le réacheminement des messages vocaux, nous recommandons à l’administrateur Exchange de configurer le standard automatique de la messagerie unifiée Exchange pour qu’il n’accepte que les messages.

Pour plus d’informations sur ces fonctionnalités, reportez-vous à [Planification de l’intégration de la messagerie unifiée Exchange dans Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Planification de la résistance Voix Entreprise dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectivement.

## Composant de routage InterCluster

Le composant de routage Intercluster est chargé d’acheminer les appels vers le pool de serveurs d’inscriptions principal du destinataire de l’appel. S’il n’est pas disponible, le composant achemine l’appel vers le pool d’inscriptions secondaire du destinataire de l’appel. Si ces deux pools ne sont pas joignables via le réseau IP, le composant de routage Intercluster réachemine l’appel vers le numéro de téléphone de l’utilisateur via la passerelle RTC.

## Autres composants du serveur frontal requis pour la voix sur IP (VoIP)

Les autres composants installé sur le serveur frontal ou le directeur qui fournissent l’essentiel de la prise en charge de la VoIP, sans être eux-mêmes des composants VoIP, sont notamment les suivants :

  - **Services d’utilisateurs** : effectuent une recherche inversée de numéros sur le numéro de téléphone de destination de chaque appel entrant et associent ce numéro à l’URI SIP de l’utilisateur de destination. À l’aide de ces informations, le composant de routage entrant dirige l’appel vers les points de terminaison SIP enregistrés de cet utilisateur. Les services d’utilisateurs représentent un composant essentiel de tous les serveurs frontaux et directeurs.

  - **Réplicateur d’utilisateurs** : extrait les numéros de téléphone des services de domaine Active Directory et les écrit dans des tables de la base de données RTC, où elles sont à la disposition des services d’utilisateurs et du serveur de carnet d’adresses. Le réplicateur d’utilisateurs est un composant essentiel de tous les serveurs frontaux.

  - **Serveur de carnet d’adresses** : fournit des données de la liste d’adresses globale provenant des services de domaine Active Directory aux clients Lync Server. Il récupère également les informations d’utilisateur et de contact de la base de données RTC, écrit ces informations dans les fichiers de carnet d’adresses, puis stocke ces fichiers dans un dossier partagé depuis lequel les clients Lync les téléchargent. Le serveur de carnet d’adresses écrit les informations dans la base de données RTCAb, utilisée par le service de requête sur le web du carnet d’adresses pour répondre aux demandes de recherche d’utilisateurs de Microsoft Lync 2010 Mobile. Il peut éventuellement normaliser les numéros de téléphone d’utilisateurs d’entreprise figurant dans la base de données RTC pour qu’ils puissent être utilisés dans Lync. Le service de carnet d’adresses est installé par défaut sur tous les serveurs frontaux. Le service de requête sur le web du carnet d’adresses est installé par défaut avec les services web sur tous les serveurs frontaux.

