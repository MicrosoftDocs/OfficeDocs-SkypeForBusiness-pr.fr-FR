---
title: 'Lync Server 2013 : Déplacement d’utilisateurs vers Voix Entreprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e92f0a7d71d42d8551a51028afec209e795941d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a>Déplacement d’utilisateurs vers Voix Entreprise dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-18_

Si vous déplacez les utilisateurs à partir d’une infrastructure de téléphonie PBX existante vers Enterprise Voice, le processus de déploiement comporte certaines étapes qui ne font pas partie du processus de planification déjà décrit dans [planification pour Enterprise Voice dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md). Pour plus d’informations sur la migration des utilisateurs d’un déploiement voix entreprise antérieur, voir les documents de migration inclus dans votre support d’installation.

Le processus de déplacement des utilisateurs à partir d’une infrastructure de téléphonie existante vers Enterprise Voice comprend les étapes suivantes :

1.  Spécifiez les numéros de téléphone principaux.

2.  activez les utilisateurs pour Voix Entreprise ;

3.  Préparer les plans de numérotation pour les utilisateurs.

4.  Planifiez les stratégies de voix des utilisateurs.

5.  Planifiez les itinéraires d’appels.

6.  Configurer le protocole PBX ou SIP Trunk pour rediriger les appels pour les utilisateurs activés pour Enterprise Voice.

7.  Déplacer les utilisateurs vers la messagerie unifiée Exchange (MU) (recommandée)

Cette rubrique décrit la planification nécessaire pour chacune de ces étapes.

<div>

## <a name="step-1-designate-primary-phone-numbers"></a>Étape 1. Désigner les numéros de téléphone principaux

Voix entreprise intègre la voix à d’autres médias de messagerie, de telle sorte qu’une fois qu’un appel entrant arrive sur le serveur, le serveur mappe le numéro à l’URI SIP de l’utilisateur, puis dévie l’appel à tous les points de terminaison client associés à cet URI SIP. Ce processus nécessite que chaque utilisateur soit associé à un numéro de téléphone principal.

Le numéro de téléphone principal doit être :

  - Globalement unique ou, dans le cas d’extensions internes, uniques au sein de l’entreprise.

  - Détenu et routable au sein de l’entreprise. Les numéros personnels ne doivent pas être utilisés.

Les utilisateurs d’entreprise peuvent avoir au moins deux numéros de téléphone répertoriés dans les services de domaine Active Directory (AD FS). Tous les numéros de téléphone associés à un utilisateur particulier peuvent être affichés ou modifiés dans la feuille de propriétés de cet utilisateur dans le composant logiciel enfichable utilisateurs et ordinateurs Active Directory.

Le champ **numéro de téléphone** de l’onglet **général** de la boîte de dialogue des propriétés de l' **utilisateur** doit contenir le numéro de poste principal de l’utilisateur. Ce numéro sera généralement désigné comme numéro de téléphone principal de l’utilisateur.

Certains utilisateurs ont des exigences spéciales (par exemple, un dirigeant qui veut que tous les appels entrants soient acheminés par l’intermédiaire d’un assistant administratif), mais ces exceptions doivent être limitées uniquement aux personnes qui ont besoin d’être claires et critiques.

Après avoir choisi un numéro principal, il doit être :

  - Normalisé au format E. 164, dans la mesure du possible.

  - Copie dans l’attribut Active Directory **msRTCSIP-Line** .
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Coexistence avec le contrôle d’appel distant (RCC)</STRONG><BR>Le RCC est la possibilité d’utiliser Lync Server pour surveiller et contrôler un téléphone de bureau PBX. Le contrôle est routé par le biais du serveur, qui sert de passerelle au PBX. Même si vous ne pouvez pas configurer un utilisateur pour les utilisateurs RCC et voix entreprise, le paramètre URI de ligne désigne le numéro de téléphone principal d’un utilisateur dans chaque cas.<BR>Si vous voulez que les utilisateurs sélectionnés disposent d’une infrastructure PBX existante, vous pouvez intégrer la voix entreprise de façon incrémentielle au sein de votre organisation. Pour plus d’informations sur ce scénario de déploiement, voir <A href="lync-server-2013-direct-sip-deployment-options.md">options de déploiement SIP directes dans Lync Server 2013</A> dans la documentation de planification.<BR>Dans les versions précédentes, vous pouviez activer les fonctions RCC et voix entreprise pour un utilisateur, mais uniquement si vous avez également configuré l’utilisateur pour le double-branchement, une fonctionnalité dans laquelle un appel entrant sonne sur le téléphone PBX d’un utilisateur et sur Communicator simultanément. Dans Lync Server 2010, le double-bifurcation n’est pas pris en charge.

    
    </div>

Il existe trois méthodes pour remplir l’attribut **msRTCSIP-Line** :

  - Serveur d’intégration d’identité Microsoft (recommandé)

  - Page **utilisateurs** du panneau de configuration de Lync Server

Lorsque de nombreux numéros de téléphone doivent être traités, un script personnalisé développé par votre organisation est le meilleur choix. En fonction de la manière dont votre organisation représente les numéros de téléphone dans les services de domaine Active Directory (AD FS), le script risque de normaliser les numéros de téléphone principaux au format E. 164 avant de les copier dans l’attribut d' **msRTCSIP-Line** .

  - Si votre organisation conserve tous les numéros de téléphone dans les services de domaine Active Directory (AD FS) dans un format unique et si ce format est E. 164, votre script doit uniquement écrire chaque numéro de téléphone principal dans l’attribut **msRTCSIP-Line** .

  - Si votre organisation conserve tous les numéros de téléphone dans les services de domaine Active Directory (AD FS) dans un format unique, mais qu’il ne s’agit pas de E. 164, votre script doit définir une règle de normalisation appropriée pour convertir les numéros de téléphone principal de leur format existant en E. 164 avant de les écrire dans l’attribut **msRTCSIP-Line** .

  - Si votre organisation n’applique pas un format standard pour les numéros de téléphone dans les services de domaine Active Directory (AD FS), votre script doit définir des règles de normalisation appropriées pour **convertir les numéros** de téléphone principal de leurs différents formats en E. 164.

Votre script devra également insérer le préfixe **tel :** avant chaque numéro principal avant de l’écrire dans l’attribut **msRTCSIP-Line** .

Le format attendu du numéro spécifié dans cet attribut est le suivant :

  - Tel : + 14255550100 ; ext = 50100.

  - Tel : 5550100 (pour les extensions uniques à l’échelle de l’entreprise)
    
    <div>
    

    > [!IMPORTANT]  
    > La normalisation réalisée par le service de carnet d’adresses (ABS) ne remplace pas ou n’entraîne pas la nécessité de normaliser le numéro de téléphone principal de chaque utilisateur dans les services de domaine Active Directory, car ABS n’a pas accès aux services de domaine Active Directory (AD DS) et ne peut donc pas copier les numéros principaux vers l’attribut <STRONG>msRTCSIP-Line</STRONG> .

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a>Étape 2. Activation des utilisateurs pour Voix Entreprise

En revanche, si vous n’avez pas besoin d’identifier les utilisateurs à activer, aucune planification spéciale n’est nécessaire pour effectuer cette étape.

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a>Étape 3. Préparer les plans de numérotation pour les utilisateurs.

Les utilisateurs qui sont activés pour voix entreprise ne seront pas en mesure de passer des appels vers le réseau PSTN sans utiliser de plan de numérotation. Un plan de numérotation est un ensemble nommé de règles de normalisation qui convertissent des numéros de téléphone pour un emplacement, un utilisateur individuel ou un objet contact nommé, en un format standard (E.164) à des fins d’autorisation téléphonique et de routage des appels. Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés en divers formats sont routés vers chaque emplacement, utilisateur ou objet contact.

Pour plus d’informations sur la préparation de plans de numérotation, voir [plans de numérotation et règles de normalisation dans Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a>Étape 4. Planifier les stratégies de voix des utilisateurs

Les paramètres de classe de service de l’utilisateur sur un PBX hérité, par exemple le droit de passer des appels longue distance ou internationaux depuis des téléphones d’entreprise, doivent être reconfigurés en tant que stratégies VoIP pour les utilisateurs transférés vers Enterprise Voice. Pour plus d’informations sur la planification et la création de stratégies pour Enterprise Voice, voir [stratégies vocales dans Lync Server 2013](lync-server-2013-voice-policies.md).

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a>Étape 5. Planifier les itinéraires des appels sortants

Les itinéraires d’appels spécifient comment Lync Server gère les appels sortants placés par des utilisateurs d’Enterprise Voice. Lorsqu’un utilisateur compose un numéro, le serveur, le cas échéant, normalise la chaîne de numérotation au format E. 164 et tente de correspondre à un URI SIP. Si le serveur ne parvient pas à établir la correspondance, il applique la logique du routage des appels sortants en fonction du numéro. Lors de la définition de cette logique, la dernière étape de la création d’un itinéraire d’appel nommé distinct pour chaque ensemble de numéros de téléphone de destination figurant dans chaque plan de numérotation.

Pour plus d’informations sur la planification des itinéraires d’appel, voir [itinéraires vocaux dans Lync Server 2013](lync-server-2013-voice-routes.md).

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a>Étape 6. Configurer le protocole PBX ou le Trunk SIP pour rediriger les appels pour les utilisateurs d’Enterprise Voice

Les utilisateurs qui étaient autrefois hébergés sur un système PBX classique ou sur une connexion SIP Trunk à un fournisseur de services de téléphonie Internet (ITSP) conservent leurs numéros de téléphone après le déplacement. La seule obligation est qu’après le déplacement, le PBX ou le Trunk SIP doit être reconfiguré pour diriger les appels entrants des utilisateurs voix entreprise vers le serveur de médiation.

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a>Étape 7. Déplacer des utilisateurs vers la messagerie unifiée Exchange (recommandé)

Le déplacement des utilisateurs vers la messagerie unifiée Exchange se compose des tâches suivantes :

  - Configurez la messagerie unifiée Exchange et Lync Server pour collaborer.

  - Permettre aux utilisateurs de répondre aux appels à la messagerie unifiée Exchange et à Outlook Voice Access. Cette tâche est exécutée sur le serveur de messagerie unifiée Exchange. Pour plus d’informations, reportez-vous à [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372)la bibliothèque TechNet du serveur Exchange 2010 à l’adresse.

</div>

</div>

<span> </span>

</div>

</div>

</div>

