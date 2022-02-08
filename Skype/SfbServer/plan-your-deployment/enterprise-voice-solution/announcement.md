---
title: Planifier l’application Annonce dans Skype Entreprise
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: Planification de l’application d’annonce dans Skype Entreprise Server Voix Entreprise, qui configure ce qu’il faut faire avec les appels téléphoniques vers des numéros de téléphone non assignés dans vos organisations. Inclut les conditions requises pour les fichiers audio.
ms.openlocfilehash: c895575a88d49bc29a74e53fac1618991b042745
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387872"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>Planifier l’application Annonce dans Skype Entreprise

Planification de l’application d’annonce dans Skype Entreprise Server Voix Entreprise, qui configure ce qu’il faut faire avec les appels téléphoniques vers des numéros de téléphone non assignés dans vos organisations. Inclut les conditions requises pour les fichiers audio.

L’application Skype Entreprise Server Announcement vous permet de configurer la gestion des appels téléphoniques entrants lorsque le numéro composé est valide pour votre organisation, mais n’est pas attribué à un utilisateur ou à un téléphone. Vous pouvez transférer ces appels vers une destination prédéterminée (numéro de téléphone, URI SIP ou messagerie vocale), lire une annonce audio, ou les deux. L’application Annonce vous permet d’éviter les situations dans lesquelles un appelant maldialisation et entend une tonalité d’occupé ou le client SIP reçoit un message d’erreur. Cette section inclut des informations de planification spécifiques à l’application Annonce

Lorsque vous déployez l’application Annonce, vous devez configurer une table de numéros non signés qui détermine l’action à prendre lorsqu’une personne compose un numéro non assigné. La table des numéros non spécifiés contient des plages de numéros de téléphone valides pour l’organisation et spécifie l’application d’annonce qui gère chaque plage. Lorsqu’un appelant compose un numéro de téléphone valide pour votre organisation mais qui n’est attribué à personne, Skype Entreprise Server recherche le numéro dans la table de routage des numéros non attribués, identifie la plage dans laquelle le numéro se trouve et approvisionnement l’appel vers l’application d’annonce spécifiée pour cette plage. L’application Annonce répond à l’appel et lit un message audio (si vous l’avez configuré pour le faire), puis déconnecte l’appel ou le transfère vers une destination prédéterminée, telle qu’un opérateur. Vous pouvez utiliser les cmdlets Skype Entreprise Server Management Shell pour configurer plusieurs messages audio ou transférer des destinations.

La manière dont vous configurez la table des numéros non attribués dépend de la façon dont vous comptez l’utiliser. Si vous avez des numéros spécifiques qui ne sont plus utilisés et que vous voulez lire des messages personnalisés pour chacun d’eux, vous pouvez entrer ces numéros spécifiques dans la table des numéros non attribués. Par exemple, si vous avez changé le numéro du bureau de service client, vous pouvez entrer l’ancien numéro du service client et l’associer à une annonce qui indique le nouveau. Si vous voulez lire un message général à quiconque appelle un numéro non attribué (comme celui d’un employé ayant quitté votre organisation), vous pouvez entrer des plages pour toutes les extensions valides de votre organisation. La table des numéros non attribués est appelée à chaque fois qu’un appelant compose un numéro qui n’est pas actuellement attribué.

## <a name="deployment-and-requirements"></a>Déploiement et conditions requises

L’application Annonce est automatiquement installée avec l’application Response Group. Les applications Annonce et Response Group sont des composants standard d’un déploiement Voix Entreprise : lorsque vous déployez Voix Entreprise, ces deux applications sont déployées automatiquement.

### <a name="software-requirements"></a>Configuration logicielle requise

Le runtime du format multimédia Windows doit être installé sur tous les serveurs frontaux ou Édition Standard qui exécutent l’application d’annonce pour les serveurs exécutant Windows Server 2008 R2 ou Microsoft Media Foundation pour les serveurs exécutant Windows Server 2012 ou Windows Server 2012  R2. Pour Windows Server 2008 R2, le runtime Windows format multimédia est installé dans le cadre de Windows Expérience utilisateur. Windows Media Format Runtime ou Microsoft Media Foundation est requis pour les fichiers Windows Media Audio (.wma) que l’application d’annonce lit pour les annonces et la musique.

### <a name="port-requirements"></a>Configuration requise pour les ports

L’application Announcement utilise **le port 5071 pour** les demandes d’écoute SIP.

> [!NOTE]
> Ce port est le paramètre par défaut, que vous pouvez modifier en utilisant la cmdlet **Set-CsApplicationServer**. Pour plus d’informations sur cette cmdlet, voir la documentation Skype Entreprise Server Management Shell.

### <a name="audio-file-requirements"></a>Conditions requises pour les fichiers audio

L’application Announcement prend en charge le format de fichier Wave (.wav) et Windows format de fichier audio multimédia (.wma) pour la musique et les annonces. Les conditions requises pour les fichiers audio pour l’application Annonce sont les mêmes que pour l’application Response Group. Pour plus d’informations, voir [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).