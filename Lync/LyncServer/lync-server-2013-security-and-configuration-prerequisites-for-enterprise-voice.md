---
title: Conditions préalables requises de configuration et de sécurité pour Voix Entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6530e00a942e2e839eaf4bc2d069212b746e2504
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Conditions préalables à la sécurité et à la configuration pour Enterprise Voice dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-18_

Vérifiez que votre infrastructure répond à la configuration requise en matière de sécurité, de configuration utilisateur et de matériel spécifique.

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a>Droits d’administration et infrastructure de certification

Assurez-vous que votre environnement est configuré avec les groupes d’utilisateurs administratifs et l’infrastructure de certification suivants à utiliser au cours du processus de déploiement voix entreprise.

  - Le déploiement d’Enterprise Voice par les administrateurs doit être membre du groupe RTCUniversalServerAdmins.

  - Les administrateurs doivent disposer des droits appropriés pour effectuer les tâches de configuration :
    
      - **CsVoiceAdministrator :** ce rôle permet à l’administrateur d’effectuer des tâches de configuration vocale, de gérer les applications vocales et d’affecter des stratégies vocales aux utilisateurs finaux.
    
      - **CsUserAdministrator :** ce rôle permet à l’administrateur de gérer les propriétés des utilisateurs, par exemple, pour activer Voix Entreprise pour un utilisateur. Ce rôle permet également à l’administrateur d’affecter des stratégies par utilisateur, à l’exception de la stratégie d’archivage, et de gérer les téléphones de partie commune et les périphériques analogiques.
    
      - **CsAdministrator :** ce rôle permet à l’utilisateur d’effectuer toutes les tâches des rôles CsVoiceAdministrator et CsUserAdministrator.
    
    <div>
    

    > [!NOTE]
    > La délégation permet à un plus grand nombre d’administrateurs de participer à votre déploiement Lync Server sans qu’il soit nécessaire d’ouvrir un accès inutile aux ressources.

    
    </div>

  - L’infrastructure MKI (Managed Key Infrastructure) est déployée et configurée à l’aide d’une infrastructure d’autorité de certification Microsoft ou tierce.
    
    <div>
    

    > [!NOTE]
    > Pour plus d’informations sur les exigences relatives aux certificats dans Lync Server, voir <A href="lync-server-2013-certificate-infrastructure-requirements.md">Configuration requise en matière d’infrastructure de certificat pour Lync Server 2013</A> dans la documentation de planification.

    
    </div>

</div>

<div>

## <a name="user-configuration"></a>Configuration utilisateur

Si vous avez localisé le serveur de médiation avec chaque pool frontal ou serveur Standard Edition au cours du déploiement frontal, les paramètres utilisateur nécessaires à l’utilisation d’Enterprise Voice étaient configurés automatiquement lors de l’installation des fichiers pour ces rôles de serveur.

Si vous venez de déployer la charge de travail voix entreprise pour le moment, avant de commencer le processus de déploiement, spécifiez le numéro de téléphone principal de chaque utilisateur que vous envisagez d’activer pour voix entreprise. En tant qu’administrateur, vous devez vous assurer que ce numéro est unique. Avant l’implémentation, tous les numéros de téléphone principal doivent être normalisés (correctement mis en forme) et copiés sur les propriétés d' **URI de ligne** de chaque utilisateur à l’aide du panneau de configuration de Lync Server.

<div>


> [!NOTE]
> Pour obtenir des exemples de numéros de téléphone principaux requis pour le déploiement d’Enterprise Voice, voir les <A href="lync-server-2013-dial-plans-and-normalization-rules.md">plans de numérotation et les règles de normalisation dans la section Lync server 2013</A> des <A href="lync-server-2013-dial-plans-and-normalization-rules.md">plans de numérotation et des règles de normalisation dans Lync Server 2013</A> dans la documentation de planification.



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Étapes suivantes : installation de fichiers ou configuration de la connectivité PSTN

Après vérification de la configuration logicielle et environnementale requise pour Enterprise Voice, vous pouvez utiliser le contenu suivant :

  - Installez le serveur de médiation, comme décrit dans [la rubrique installer les fichiers pour le serveur de médiation dans Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), mais uniquement si vous voulez déployer un serveur ou un pool de médiation autonome, car les serveurs de médiation sont installés dans le cadre du processus de déploiement de l’application frontale ou du pool frontal.

  - Vous pouvez aussi commencer à configurer des paramètres pour acheminer les appels pour les utilisateurs d’Enterprise Voice, comme décrit dans la rubrique [Configuration des Trunks dans Lync Server 2013](lync-server-2013-configuring-trunks.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

