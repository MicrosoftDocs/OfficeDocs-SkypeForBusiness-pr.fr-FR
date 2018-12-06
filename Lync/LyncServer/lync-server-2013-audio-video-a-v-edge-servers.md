---
title: Serveurs Edge Audio/Vidéo (A/V) dans Lync Server 2013
TOCTitle: Serveurs Edge Audio/Vidéo (A/V) dans Lync Server 2013
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49891499
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Serveurs Edge Audio/Vidéo (A/V) dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Le service Edge A/V permet à vos utilisateurs internes (les utilisateurs connectés au réseau de votre organisation) de partager des fichiers audio et vidéo avec des utilisateurs externes (des utilisateurs qui ne sont pas connectés au réseau de votre organisation). Outre les données audio et vidéo, le service Edge A/V fournit également une prise en charge du partage du Bureau et du transfert de fichiers.

La gestion du service Edge A/V s’effectue à l’aide de la configuration de ce service. Ces paramètres vous permettent de gérer la quantité maximale de bande passante à allouer par port et par utilisateur, ainsi que de spécifier la durée pendant laquelle un jeton d’authentification peut être utilisé avant de devoir être renouvelé. Les paramètres de configuration Edge A/V peuvent être appliqués à des sites ou à des serveurs Edge A/V individuels. Lors de la détermination de la collection de paramètres qui sera prioritaire, utilisez le guide suivant :

  - Les paramètres configurés au niveau du service (c’est-à-dire sur un serveur) prévalent sur tous les autres paramètres.

  - Les paramètres configurés au niveau du site prévalent sur les paramètres configurés au niveau global. Les paramètres au niveau du service, quant à eux, prévalent sur les paramètres au niveau du site.

  - Les paramètres au niveau global seront utilisés uniquement si aucun autre paramètre du service n’est configuré sur le serveur et s’il n’existe aucun paramètre pour le site où ce serveur est situé.

Le service Edge A/V ne peut être géré qu’à l’aide de Lync Server PowerShell et des applets de commande CsAVEdgeConfiguration.

## Dans cette section

  - [Renvoi des informations de configuration du serveur Edge A/V](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [Création ou modification d’une collection de paramètres de configuration de serveur Edge A/V](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [Suppression d’une collection existante de paramètres de configuration d’un serveur Edge A/V](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

