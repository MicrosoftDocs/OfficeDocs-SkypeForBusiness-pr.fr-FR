---
title: Planifier l’application d’annonce dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: Planification de l’application d’annonce dans Skype entreprise Server voix entreprise, qui configure ce qu’il faut faire avec les appels téléphoniques pour les numéros de téléphone non affectés au sein de votre organisation. Cela inclut les conditions requises pour les fichiers audio.
ms.openlocfilehash: af7ce9fdcfa78daa875a4748eafac5020246b74b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277131"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>Planifier l’application d’annonce dans Skype entreprise

Planification de l’application d’annonce dans Skype entreprise Server voix entreprise, qui configure ce qu’il faut faire avec les appels téléphoniques pour les numéros de téléphone non affectés au sein de votre organisation. Cela inclut les conditions requises pour les fichiers audio.

L’application annonce de Skype entreprise Server vous permet de configurer la gestion des appels téléphoniques entrants lorsque le numéro numéroté est valide pour votre organisation, mais qu’il n’est pas attribué à un utilisateur ou à un téléphone. Vous pouvez transférer ces appels vers une destination prédéterminée (numéro de téléphone, URI SIP ou messagerie vocale), lire une annonce audio, ou les deux. L’application d’annonce permet d’éviter les situations dans lesquelles un appelant compose un mauvais numéro et entend une tonalité de ligne occupée, ou lorsque le client SIP reçoit un message d’erreur. Cette section comprend des informations de planification spécifiques à l’application d’annonce.

Lorsque vous déployez l’application d’annonce, vous devez configurer une table numérotée non assignée qui détermine l’action à entreprendre lorsque quelqu’un compose un numéro non attribué. La table numéro non affecté contient des plages de numéros de téléphone valides pour l’organisation et spécifie l’application d’annonce qui gère chaque plage. Lorsqu’un utilisateur compose un numéro de téléphone valide pour votre organisation, mais qu’il n’est pas attribué à une personne, Skype entreprise Server recherche le numéro dans la table de routage des numéros non attribués, identifie la plage dans laquelle se trouve le numéro et achemine l’appel vers le Application d’annonce spécifiée pour cette plage. L’application d’annonce répond à l’appel et lit un message audio (si vous l’avez configurée), puis déconnecte l’appel ou le transfère à une destination prédéfinie (par exemple, un opérateur). Vous pouvez utiliser les applets de cmdlet Skype entreprise Server Management Shell pour configurer plusieurs messages audio ou pour transférer des destinations.

La manière dont vous configurez la table des numéros non attribués dépend de la façon dont vous comptez l’utiliser. Si vous avez des numéros spécifiques qui ne sont plus utilisés et que vous voulez lire des messages personnalisés pour chacun d’eux, vous pouvez entrer ces numéros spécifiques dans la table des numéros non attribués. Par exemple, si vous avez changé le numéro du bureau de service client, vous pouvez entrer l’ancien numéro du service client et l’associer à une annonce qui indique le nouveau. Si vous voulez lire un message général à quiconque appelle un numéro non attribué (comme celui d’un employé ayant quitté votre organisation), vous pouvez entrer des plages pour toutes les extensions valides de votre organisation. La table des numéros non attribués est appelée à chaque fois qu’un appelant compose un numéro qui n’est pas actuellement attribué.

## <a name="deployment-and-requirements"></a>Déploiement et exigences

L’application d’annonce est automatiquement installée avec l’application Response Group. Les applications d’annonce et de groupe de réponse sont des composants standard d’un déploiement voix entreprise: lorsque vous déployez une voix entreprise, ces deux applications sont déployées automatiquement.

### <a name="software-requirements"></a>Configuration logicielle requise

Tous les serveurs front-end ou les serveurs Standard Edition qui exécutent l’application d’annonce doivent avoir installé le runtime du format Windows Media pour les serveurs exécutant Windows Server 2008 R2 ou Microsoft Media Foundation pour les serveurs exécutant Windows Server 2012 ou Windows Server 2012 R2. Pour Windows Server 2008 R2, le runtime Windows Media Format Runtime est installé dans le cadre de l’expérience de bureau Windows. Windows Media Format Runtime ou Microsoft Media Foundation est requis pour les fichiers Windows Media audio (. WMA) que l’application d’annonce exécute pour les annonces et la musique.

### <a name="port-requirements"></a>Configuration requise pour les ports

L’application d’annonce utilise le **Port 5071** pour les demandes d’écoute SIP.

> [!NOTE]
> Ce port est le paramètre par défaut, que vous pouvez modifier en utilisant l’applet de commande **Set-CsApplicationServer**. Pour plus d’informations sur cette applet de connexion, consultez la documentation de Skype entreprise Server Management Shell.

### <a name="audio-file-requirements"></a>Conditions requises pour les fichiers audio

L’application d’annonce prend en charge le format de fichier Wave (. wav) et le format de fichier Windows Media audio (. WMA) pour la musique et les annonces. La configuration requise pour le fichier audio pour l’application d’annonce est identique à celle de l’application Response Group. Pour plus d’informations, reportez-vous à [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).


