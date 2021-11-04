---
title: Expanseur des paramètres de noms de domaine complets du serveur Edge
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
description: Pour modifier ou spécifier des Paramètres externes pour les serveurs Edge, vous devez d’abord déterminer si vous allez utiliser des adresses IP distinctes pour l’accès SIP (Session Initiation Protocol), le service Edge de conférence Web et le service Edge audio/vidéo.
ms.openlocfilehash: d9404821e8ab1f11014a05030ea9007ad5150a02
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60739250"
---
# <a name="edge-server-fqdns-settings-expander"></a>Expandeur des paramètres de noms de domaine complets du serveur Edge

Pour modifier ou spécifier des **Paramètres** externes pour les serveurs Edge, vous devez d’abord déterminer si vous allez utiliser des adresses IP distinctes pour l’accès SIP (Session Initiation Protocol), le service Edge de conférence Web et le service Edge audio/vidéo.

Si vous envisagez d’utiliser des adresses IP distinctes à chaque fois, activez la case à cocher **Activer un nom de domaine complet et une adresse IP distincts pour la conférence Web et A/V**. Chaque service doit disposer d’un enregistrement d’hôte DNS (A) correspondant créé pour cela.

Pour chacun des services côté externe, spécifiez un nom de domaine complet (FQDN) et un port associé. Par exemple, pour **Accès SIP**, vous pouvez utiliser sip.contoso.com avec un port 5061 associé.

> [!IMPORTANT]
> Si vous sélectionnez des noms de domaine complets distincts pour chaque service côté externe, chacun de ces services devra avoir une valeur de port unique associée. Par défaut, SIP se situe sur le port 5061/TLS, le service Edge de conférence web se situe sur le port 444/TLS et le service Edge de conférence A/V se situe sur le port 443/TLS. Si vous apportez des modifications à l’un de ces paramètres, y compris l’utilisation d’un nom de domaine complet et d’adresses IP ou de ports distincts, vous devez mettre à jour tous les autres services qui s’appuient sur les valeurs initialement configurées.

Si vous déterminez que votre organisation utilisera un nom de domaine complet et une adresse IP uniques pour les services côté externe, désactivez la case à cocher **Activer un nom de domaine complet et une adresse IP distincts pour la conférence web et les fonctionnalités audio/vidéo**. Vous pouvez ensuite modifier les valeurs du nom de domaine complet du port et du pool **Accès SIP**, si nécessaire.

> [!IMPORTANT]
> Si vous apportez des modifications à l’un de ces paramètres, y compris l’utilisation d’un nom de domaine complet et d’adresses IP ou de ports distincts, vous devez mettre à jour tous les autres services qui s’appuient sur les valeurs initialement configurées.

Pour plus d’informations sur la définition et la configuration des paramètres des services Edge, voir [Définir votre topologie Edge.](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)