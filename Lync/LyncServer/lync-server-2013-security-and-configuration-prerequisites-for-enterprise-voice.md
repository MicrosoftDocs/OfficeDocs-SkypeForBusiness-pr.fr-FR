---
title: Conditions préalables de configuration et de sécurité pour voix entreprise
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
ms.openlocfilehash: aa8f0f3dd113b10a01f18a0542561de946d4acd0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510471"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Conditions préalables de configuration et de sécurité pour voix entreprise dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-18_

Vérifiez que votre infrastructure est conforme aux conditions préalables suivantes en matière de sécurité, de configuration utilisateur et de matériel pour des scénarios spécifiques.

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a>Droits d’administration et infrastructure de certificats

Assurez-vous que votre environnement est configuré avec les groupes d’administrateurs et l’infrastructure de certificats suivants à utiliser au cours du processus de déploiement de Voix Entreprise.

  - Les administrateurs déployant Voix Entreprise doivent être membres du groupe RTCUniversalServerAdmins.

  - Les administrateurs doivent disposer des droits appropriés pour effectuer les tâches de configuration :
    
      - **CsVoiceAdministrator :** Ce rôle permet à l’administrateur d’effectuer des tâches de configuration vocale, de gérer les applications vocales et d’affecter des stratégies vocales aux utilisateurs finaux.
    
      - **CsUserAdministrator :** Ce rôle permet à l’administrateur de gérer les propriétés des utilisateurs, par exemple, pour activer Voix Entreprise pour un utilisateur. Ce rôle permet également à l’administrateur d’affecter des stratégies par utilisateur, à l’exception de la stratégie d’archivage, et de gérer les téléphones de partie commune et les périphériques analogues.
    
      - **CsAdministrator :** Ce rôle permet à l’utilisateur d’effectuer toutes les tâches des rôles CsVoiceAdministrator et CsUserAdministrator.
    
    <div>
    

    > [!NOTE]
    > La délégation permet à un plus grand nombre d’administrateurs de participer à votre déploiement Lync Server sans avoir à ouvrir un accès inutile aux ressources.

    
    </div>

  - L’infrastructure MKI (Managed Key Infrastructure) est déployée et configurée, à l’aide d’une infrastructure d’autorité de certification Microsoft ou tierce.
    
    <div>
    

    > [!NOTE]
    > Pour plus d’informations sur les certificats requis dans Lync Server, voir <A href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure Requirements for Lync Server 2013</A> dans la documentation de planification.

    
    </div>

</div>

<div>

## <a name="user-configuration"></a>Configuration utilisateur

Si vous avez colocalisé le serveur de médiation avec chaque pool frontal ou serveur Standard Edition pendant le déploiement frontal, les paramètres utilisateur nécessaires pour voix entreprise ont été configurés automatiquement lors de l’installation des fichiers pour ces rôles serveur.

Si vous procédez à un nouveau déploiement de la charge de travail de Voix Entreprise, avant de commencer le processus de déploiement, désignez un numéro de téléphone principal pour chaque utilisateur pour lequel vous envisagez d’activer Voix Entreprise. En tant qu’administrateur, vous devez vous assurer que ce numéro est unique. Avant l’implémentation, tous les numéros de téléphone principaux doivent être normalisés (correctement mis en forme) et copiés dans la propriété **URI de ligne** de chaque utilisateur à l’aide du panneau de configuration Lync Server.

<div>


> [!NOTE]
> Pour obtenir des exemples de numéros de téléphone principaux requis pour le déploiement de voix entreprise, voir la section <A href="lync-server-2013-dial-plans-and-normalization-rules.md">plans de numérotation et règles de normalisation dans la section Lync server 2013</A> des <A href="lync-server-2013-dial-plans-and-normalization-rules.md">plans de numérotation et des règles de normalisation dans Lync Server 2013</A> dans la documentation de planification.



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Étapes suivantes : installer les fichiers ou configurer la connectivité PSTN

Après avoir vérifié que les logiciels requis sont disponibles et que votre environnement répond aux conditions préalables pour le déploiement de Voix Entreprise, vous pouvez utiliser le contenu suivant pour :

  - Installez le serveur de médiation, comme décrit dans [install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), uniquement si vous souhaitez déployer un serveur de médiation ou un pool autonome, car les serveurs de médiation sont installés dans le cadre du processus de déploiement du pool frontal ou du serveur Standard Edition lorsqu’ils sont colocalisés.

  - Vous pouvez aussi commencer à configurer les paramètres pour acheminer les appels pour les utilisateurs de voix entreprise, comme décrit dans la rubrique [Configuring Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

