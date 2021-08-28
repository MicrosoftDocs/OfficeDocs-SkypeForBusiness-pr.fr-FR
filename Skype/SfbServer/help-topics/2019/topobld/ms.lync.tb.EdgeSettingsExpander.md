---
title: Expanseur des paramètres du pool de serveurs Edge
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
ROBOTS: NOINDEX, NOFOLLOW
description: 'Les sections suivantes vous permettent de modifier les paramètres d’un pool Edge de serveur unique ou de serveurs multiples :'
ms.openlocfilehash: 9d1f133a2f0c8c469c0fb399f46cd3030035629b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593918"
---
# <a name="edge-settings-expander"></a>Expandeur des paramètres du pool de serveurs Edge

Les sections suivantes vous permettent de modifier les paramètres d’un pool Edge de serveur unique ou de serveurs multiples :

- Paramètres généraux

- Paramètres de sélection du tronçon suivant

- Configuration du serveur Edge


## <a name="general-settings"></a>Paramètres généraux

Nom de domaine complet (FQDN) du pool interne pour le pool de serveurs Edge. Modifiez le nom de domaine complet du pool pour changer ce paramètre.

Activez la case à cocher Activer la fédération pour ce **pool Edge (port 5061)** si vous souhaitez configurer la fédération avec un serveur Skype Entreprise Server 2015.

Spécifiez le numéro de port pour **Port de réplication de configuration interne (HTTPS)**.

## <a name="next-hop-selection-settings"></a>Paramètres de sélection du tronçon suivant

Pour définir ou modifier le **pool** du saut suivant que les serveurs Edge utiliseront pour communiquer avec l’infrastructure interne, sélectionnez un directeur, un pool directeur, un serveur frontal ou un pool de serveurs frontux dans la zone de liste liste. Seuls les directeurs ou les fronts qui ont été configurés dans le Générateur de topologies s’affichent pour la sélection.

## <a name="edge-server-configuration"></a>Configuration du serveur Edge

Pour modifier ou spécifier des paramètres pour les **Paramètres externes** des serveurs Edge, vous devez déterminer si vous allez utiliser des adresses IP séparées pour l’accès SIP, la conférence web et le service audio/vidéo.

Si vous envisagez d’utiliser des adresses IP distinctes à chaque fois, activez la case à cocher **Activer un nom de domaine complet et une adresse IP distincts pour la conférence web et les fonctionnalités audio/vidéo**. Un enregistrement DNS A (hôte) doit avoir été créé pour chaque service.

Pour chaque service externe, vous spécifiez un nom de domaine complet et un port associé. Par exemple, l’**Accès SIP** utilise sip.contoso.com avec un port associé de 5061.

> [!IMPORTANT]
> Si vous sélectionnez des noms de domaine complets distincts pour chaque service côté externe, chacun de ces services devra avoir une valeur de port unique associée. Par défaut, le SIP est sur le port 5061/TLS, le service Edge de conférence web est sur le port 444/TLS et le serveur de conférence A/V sur le port 443/TLS. Si vous apportez des modifications à l’un de ces paramètres, y compris l’utilisation d’un nom de domaine complet et d’adresses IP ou de ports distincts, vous devez mettre à jour tous les autres services qui s’appuient sur les valeurs initialement configurées.

Si vous déterminez que votre organisation utilisera un nom de domaine complet et une adresse IP uniques pour les services côté externe, désactivez la case à cocher **Activer un nom de domaine complet et une adresse IP distincts pour la conférence web et les fonctionnalités audio/vidéo**. Vous pouvez ensuite modifier les valeurs du nom de domaine complet du pool et du port **Accès SIP**, si nécessaire.

> [!IMPORTANT]
> Si vous apportez des modifications à l’un de ces paramètres, y compris l’utilisation d’un nom de domaine complet et d’adresses IP ou de ports distincts, vous devez mettre à jour tous les autres services qui s’appuient sur les valeurs initialement configurées.

## <a name="see-also"></a>Voir aussi

Pour plus d’informations sur la définition et la configuration des paramètres des services Edge, voir [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)