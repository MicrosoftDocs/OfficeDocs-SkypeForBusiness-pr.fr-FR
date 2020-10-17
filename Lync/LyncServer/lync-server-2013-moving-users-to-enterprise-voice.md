---
title: 'Lync Server 2013 : transfert d’utilisateurs vers voix entreprise'
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
ms.openlocfilehash: 3dfd2507f57265b53beea6f84d07760d35abe6e3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507051"
---
# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a>Transfert d’utilisateurs vers voix entreprise dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-18_

Si vous déplacez des utilisateurs d’une infrastructure de téléphonie PBX existante vers voix entreprise, le processus de déploiement inclut certaines étapes qui ne font pas partie du processus de planification déjà décrit dans [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md). Pour plus d’informations sur la migration des utilisateurs d’un déploiement antérieur de Voix Entreprise, voir les documents de migration inclus dans votre support d’installation.

Le processus de déplacement d’utilisateurs à partir d’une infrastructure téléphonique existante vers Voix Enterprise comprend les étapes suivantes :

1.  Indiquer les numéros de téléphone principaux.

2.  activez les utilisateurs pour Voix Entreprise ;

3.  Préparer les plans de numérotation des utilisateurs.

4.  Planifier des stratégies de voix utilisateur.

5.  Planifier des itinéraires téléphoniques.

6.  Configurer le système PBX ou la jonction SIP pour rediriger les appels destinés aux utilisateurs activés pour Voix Entreprise.

7.  Déplacez les utilisateurs vers la messagerie unifiée Exchange (messagerie unifiée) (recommandé).

Cette rubrique décrit la planification nécessaire à chacune de ces étapes.

<div>

## <a name="step-1-designate-primary-phone-numbers"></a>Étape 1 : indiquer les numéros de téléphone principaux

Voix Entreprise intègre la voix à d’autres médias de messagerie ; par exemple, lorsqu’un appel entrant arrive sur le serveur, celui-ci mappe le numéro sur l’URI SIP de l’utilisateur, puis dirige l’appel vers tous les systèmes d’extrémité clients associés à cet URI SIP. Ce processus requiert que chaque utilisateur soit associé à un numéro de téléphone principal.

Un numéro de téléphone principal doit :

  - être globalement unique ou, dans le cas de numéros de postes internes, unique dans l’entreprise ;

  - appartenir à l’entreprise et y être routable. Les numéros personnels ne doivent pas être utilisés.

Les utilisateurs d’entreprise peuvent avoir au moins deux numéros de téléphone dans les services de domaine Active Directory. Tous les numéros de téléphone associés à un utilisateur particulier peuvent être affichés ou modifiés dans la feuille de propriétés de cet utilisateur, dans le composant logiciel enfichable Utilisateurs et ordinateurs Active Directory.

La zone **Numéro de téléphone** située sous l’onglet **Général** de la boîte de dialogue **Propriétés de l’utilisateur** doit contenir le numéro professionnel principal de l’utilisateur. Ce numéro est habituellement indiqué comme numéro de téléphone principal de l’utilisateur.

Certains utilisateurs peuvent avoir des exigences particulières (par exemple, un cadre qui veut que tous les appels entrants soient routés par le biais d’un assistant administratif), mais de telles exceptions doivent se limiter à des cas où le besoin est précis et essentiel.

Une fois qu’un numéro principal est choisi, il doit être :

  - normalisé au format E.164, si possible ;

  - copié dans l’attribut Active Directory **msRTCSIP-line**.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Coexistence avec le contrôle d’appel distant</STRONG><BR>Le RCC est la possibilité d’utiliser Lync Server pour surveiller et contrôler un téléphone PBX de bureau. Le contrôle est routé par le serveur, qui joue le rôle de passerelle vers le système PBX. Bien que vous ne puissiez pas configurer un utilisateur à la fois pour le contrôle d’appel distant et Voix Entreprise, le paramètre URI de ligne spécifie un numéro de téléphone principal de l’utilisateur dans un cas comme dans l’autre.<BR>Si vous disposez d’une infrastructure PBX existante et que vous voulez que certains utilisateurs sélectionnés continuent à l’utiliser, vous pouvez introduire Voix Entreprise de manière incrémentielle dans votre organisation. Pour plus d’informations sur ce scénario de déploiement, voir <A href="lync-server-2013-direct-sip-deployment-options.md">options de déploiement SIP direct dans Lync Server 2013</A> dans la documentation de planification.<BR>Dans les versions précédentes, vous pouviez activer le RCC et la voix entreprise pour un utilisateur, mais seulement si vous avez également configuré l’utilisateur pour la double bifurcation, une fonctionnalité dans laquelle un appel entrant sonnera simultanément sur le téléphone PBX d’un utilisateur et sur Communicator. Dans Lync Server 2010, la double interplication n’est pas prise en charge.

    
    </div>

Il existe trois façons de renseigner l’attribut **msRTCSIP-line** :

  - serveur MIIS (Microsoft Identity Integration Server) (recommandé) ;

  - Page **utilisateurs** dans le panneau de configuration Lync Server

Lorsqu’un grand nombre de numéros de téléphone doivent être traités, un script personnalisé développé par votre organisation est le meilleur choix. En fonction de la façon dont votre organisation affiche les numéros de téléphone dans les services de domaine Active Directory, le script devra peut-être normaliser les numéros de téléphone principaux au format E.164 avant de les copier dans l’attribut **msRTCSIP-line**.

  - Si votre organisation gère tous les numéros de téléphone dans les services de domaine Active Directory sous un seul format et si ce format est E.164, il suffit que votre script écrive chaque numéro de téléphone principal dans l’attribut **msRTCSIP-line**.

  - Si votre organisation gère tous les numéros de téléphone dans les services de domaine Active Directory sous un seul format, mais que ce format n’est pas E.164, votre script doit définir une règle de normalisation appropriée pour convertir les numéros de téléphone principaux sous leur format existant au format E.164 avant de les écrire dans l’attribut **msRTCSIP-line**.

  - Si votre organisation n’applique pas de format standard pour les numéros de téléphone dans les services de domaine Active Directory, votre script doit définir des règles de normalisation appropriées pour convertir les numéros de téléphone principaux au format E.164 avant de les écrire dans l’attribut **msRTCSIP-line**.

Votre script doit également insérer le préfixe **Tel: ** avant chaque numéro principal avant de l’écrire dans l’attribut **msRTCSIP-line**.

Le format attendu du numéro spécifié dans cet attribut est :

  - Tél : + 14255550100 ; ext = 50100.

  - Tel:5550100 (pour les postes uniques à l’échelle de l’entreprise)
    
    <div>
    

    > [!IMPORTANT]  
    > La normalisation effectuée par le Service de carnet d’adresses ne remplace, ni n’élimine le besoin de normaliser le numéro de téléphone principal de chaque utilisateur dans les services de domaine Active Directory, car le Service de carnet d’adresses n’a pas accès à ces services et ne peut, par conséquent, pas copier les numéros principaux dans l’attribut <STRONG>msRTCSIP-line</STRONG>.

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a>Étape 2 : activer les utilisateurs pour Voix Entreprise

Une fois que vous avez identifié les utilisateurs à activer, aucune planification spéciale n’est requise pour effectuer cette étape.

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a>Étape 3 : préparer les plans de numérotation des utilisateurs.

Les utilisateurs activés pour Voix Entreprise ne pourront pas passer d’appel sur le réseau téléphonique commuté sans la mise en place de plans de numérotation. Un plan de numérotation est un ensemble nommé de règles de normalisation qui convertissent des numéros de téléphone pour un emplacement, un utilisateur individuel ou un objet contact nommé, en un format standard (E.164) à des fins d’autorisation téléphonique et de routage des appels. Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés en divers formats sont routés vers chaque emplacement, utilisateur ou objet contact.

Pour plus d’informations sur la préparation des plans de numérotation, voir [Dial plans and Normalization Rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a>Étape 4. Planifier les stratégies de voix utilisateur

Les paramètres de classe de service utilisateur du système PBX hérité, tels que l’autorisation à passer des appels longue distance ou internationaux depuis les téléphones de la société, doivent être reconfigurés en tant que stratégies VoIP pour les utilisateurs déplacés vers Voix Entreprise. Pour plus d’informations sur la planification et la création de stratégies pour voix entreprise, voir [stratégies de voix dans Lync Server 2013](lync-server-2013-voice-policies.md).

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a>Étape 5. Planifier les itinéraires d’appels sortants

Les itinéraires d’appels définissent la façon dont Lync Server gère les appels sortants passés par des utilisateurs voix entreprise. Lorsqu’un utilisateur compose un numéro, le serveur, si nécessaire, normalise la chaîne de numérotation au format E.164 et tente de le mettre en correspondance avec un URI SIP. Si le serveur ne parvient pas à établir de correspondance, il applique la logique de routage des appels sortants en fonction du numéro. Dernière étape de la définition : la logique crée un itinéraire téléphonique nommé distinct pour chaque ensemble de numéros de téléphone de destination répertorié dans chaque plan de numérotation.

Pour plus d’informations sur la planification des itinéraires d’appels, consultez la rubrique [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a>Étape 6. Configurer un PBX ou une jonction SIP pour réacheminer les appels pour les utilisateurs de voix entreprise

Les utilisateurs qui étaient auparavant hébergés sur un système PBX traditionnel ou une connexion de jonction SIP auprès d’un fournisseur de services de téléphonie Internet conservent leurs numéros de téléphone après le déplacement. Le seul besoin est qu’après le déplacement, le PBX ou la jonction SIP doit être reconfigurée pour acheminer les appels entrants pour les utilisateurs voix entreprise vers le serveur de médiation.

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a>Étape 7 : déplacer des utilisateurs vers la messagerie unifiée Exchange (recommandé)

Le déplacement d’utilisateurs vers la messagerie unifiée Exchange comprend les tâches suivantes :

  - Configurez la messagerie unifiée Exchange et Lync Server pour qu’ils fonctionnent ensemble.

  - Activer les utilisateurs pour le répondeur automatique de la messagerie unifiée Exchange et Outlook Voice Access. Cette tâche est effectuée sur le serveur de messagerie unifiée Exchange. Pour plus d’informations, reportez-vous à la bibliothèque TechNet Exchange Server 2010 à l’adresse [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

