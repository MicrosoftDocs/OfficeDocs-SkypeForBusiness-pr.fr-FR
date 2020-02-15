---
title: Composants et topologies Lync Server 2013 pour les conférences
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d14c12ad1e28dc2a40fed5b19b5928a5bedc069
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a>Composants et topologies pour les conférences dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-04_

Lorsque vous sélectionnez Conférence dans le générateur de topologie, la fonctionnalité de conférence est déployée dans le cadre du serveur frontal ou du serveur Standard Edition. La Conférence rendez-vous et le partage PowerPoint nécessitent des composants et une configuration supplémentaires. Les sections suivantes décrivent les composants et topologies pris en charge pour la conférence Web, la conférence A/V et la Conférence rendez-vous.

<div>

## <a name="supported-components"></a>Composants pris en charge

Les seuls composants conférence Web et conférence A/V requis sont les serveurs frontaux ou les serveurs Standard Edition de votre organisation. Pour obtenir la liste des configurations matérielle et logicielle requises pour les serveurs frontaux et les serveurs Standard Edition, reportez-vous à la rubrique Hardware Supported [for Lync server 2013](lync-server-2013-supported-hardware.md) and [Server Software and Infrastructure Support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).

Lync Server 2013 utilise Office Web Apps et Office Web Apps Server pour gérer le partage et le rendu des présentations PowerPoint. Pour plus d’informations sur l’installation et la configuration d’Office Web Apps Server, voir Configuration de l' [intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Outre la configuration requise pour la conférence Web et la conférence A/V, la Conférence rendez-vous utilise les composants Lync Server 2013 suivants :

  - **Application service**   application service fournit une plateforme pour le déploiement, l’hébergement et la gestion des applications de communications unifiées. La Conférence rendez-vous utilise deux applications de communications unifiées qui nécessitent le service d’application : annonce du surveillant de conférence et de la Conférence. Le service d’application est installé et activé par défaut sur chaque serveur frontal dans un pool frontal et sur chaque serveur Standard Edition Server lorsque vous déployez une charge de travail Conférence et sélectionnez l’option de conférence rendez-vous.

  - ****   L’application de surveillance de conférence d’application du service de conférence est une application de communications unifiées qui accepte les appels PSTN (réseau téléphonique commuté), lance des invites et joint les appels à une conférence a/V. L’application de surveillance de conférence est installée et activée par défaut lorsque vous déployez une charge de travail de conférence et sélectionnez l’option Conférence rendez-vous.

  - **Annonce de conférence**   l’application d’annonce de conférence d’applications est une application de communications unifiées qui diffuse des tonalités et des invites aux participants PSTN sur certaines actions, comme lorsque les participants rejoignent ou quittent une conférence, les participants sont activés ou désactivés, une personne entre dans la salle d’attente ou la Conférence est verrouillée ou déverrouillée. L’application d’annonce de conférence prend également en charge les commandes de numérotation en fréquences vocales (DTMF) à partir du clavier du téléphone. L’application d’annonce de conférence est automatiquement installée et activée par défaut lorsque vous déployez une charge de travail de conférence et sélectionnez l’option Conférence rendez-vous.

  - **Page Paramètres de conférence**   rendez-vous la page Paramètres de conférence rendez-vous affiche les numéros de conférence rendez-vous avec leurs langues disponibles, les informations de conférence affectées (c’est-à-dire pour les réunions qui n’ont pas besoin d’être planifiées) et les contrôles DTMF de conférence, et prend en charge la gestion des informations sur les conférences et les numéros de conférence associés. La page Paramètres de conférence rendez-vous est automatiquement installée dans le cadre des services Web.

  - **Lync Server 2013, serveur de médiation et**   Conférence rendez-vous de passerelle PSTN nécessite un serveur de médiation pour traduire la signalisation (et les médias, dans certaines configurations) entre Lync Server 2013 et la passerelle PSTN, ainsi qu’une passerelle PSTN pour traduire la signalisation et les médias entre le serveur de médiation et la passerelle PSTN. Pour la Conférence rendez-vous, vous devez déployer au moins un serveur de médiation et au moins l’un des éléments suivants :
    
      - Passerelle PSTN
    
      - IP-PBX
    
      - Contrôleur de frontière de session (SBC) (pour un fournisseur de services de téléphonie Internet auquel vous vous connectez en configurant une jonction SIP)
    
    <div>
    

    > [!NOTE]  
    > Si vous déployez également voix entreprise, le serveur de médiation et les passerelles RTC font partie du déploiement voix entreprise. Si vous déployez pas Voix Entreprise, vous devez déployer au moins un serveur de médiation et une passerelle PSTN, un système IP-PBX ou un contrôleur de frontière de session pour la conférence rendez-vous.

    
    </div>

  - ****   Le magasin de fichiers du magasin de fichiers est utilisé pour les fichiers audio de nom enregistrés. Le magasin de fichiers est un composant standard dans chaque déploiement Enterprise Edition ou Standard Edition.

  - ****   Le magasin d’utilisateurs du magasin d’utilisateurs est utilisé pour stocker les codes confidentiels de l’utilisateur Lync Server 2013. Les codes confidentiels sont hachés. Le magasin d’utilisateurs est un composant standard dans chaque déploiement Enterprise Edition ou Standard Edition.

  - **Panneau de configuration Lync Server**   certains paramètres de rendez-vous peuvent être configurés à l’aide du panneau de configuration Lync Server.

  - **Lync Server Management Shell**   tous les paramètres de rendez-vous peuvent être configurés à l’aide des applets de commande Lync Server Management Shell. Les applets de commande Lync Server Management Shell sont disponibles pour le déploiement, la configuration, l’exécution, la surveillance et le dépannage de l’application de surveillance de conférence et de l’application de conférence. Pour plus d’informations sur les cmdlets spécifiques, reportez-vous à la documentation Lync Server Management Shell.

</div>

<div>

## <a name="supported-topologies"></a>Topologies prises en charge

Dans Lync Server 2013, le serveur qui exécute les services de conférence est toujours colocalisé avec les serveurs frontaux ou les serveurs Standard Edition. Lors du déploiement initial, le générateur de topologie vous offre la possibilité d’inclure des conférences dans votre topologie. Vous pouvez également utiliser le générateur de topologie pour ajouter des conférences à un déploiement existant. Pour plus d’informations, reportez-vous à [la rubrique définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

<div>

## <a name="dial-in-conferencing-toplogies"></a>Topologies de conférence rendez-vous

Vous pouvez déployer la Conférence rendez-vous dans les topologies et configurations suivantes :

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

  - Avec ou sans voix entreprise

Vous pouvez déployer une application de service d’applications, de surveillance de conférence et d’annonce de conférence dans un site central, mais pas dans un site de succursale.

<div>


> [!NOTE]  
> Si vous déployez la Conférence rendez-vous, vous devez la déployer dans tous les pools où vous déployez les conférences Lync Server 2013. Vous n’avez pas besoin d’attribuer des numéros d’accès dans chaque pool, mais vous devez déployer la fonctionnalité de conférence rendez-vous dans chaque pool. Cette exigence prend en charge la fonctionnalité de nom enregistré lorsqu’un utilisateur appelle un numéro d’accès à partir d’un pool pour joindre une conférence Lync Server 2013 dans un autre pool.



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a>Topologies prises en charge pour Lync Server 2013 et Office Web Apps

Lync Server 2013 fournit les méthodes suivantes pour configurer Office Web Apps Server. En fonction de vos besoins, vous pouvez :

  - **Installez Lync Server 2013 et Office Web Apps Server sur site derrière le pare-feu de votre organisation et dans la même zone réseau.** Avec cette topologie, l’accès externe au serveur Office Web Apps Server sera fourni par le biais de votre serveur proxy inverse. Lync Server 2013 et Office Web Apps Server (ou une batterie Office Web Apps Server) sont installés sur site et derrière le pare-feu de votre organisation. Idéalement, vous devez installer Office Web Apps Server dans la même zone de réseau que Lync Server.
    
    Les clients Lync externes peuvent se connecter à Lync Server 2013 et à Office Web Apps Server à l’aide d’un serveur proxy inverse, qui est un serveur qui prend des demandes en provenance d’Internet et les transmet au réseau interne. (Les clients internes n’ont pas besoin d’utiliser le serveur proxy inverse, car ils peuvent se connecter directement à Office Web Apps Server.) Cette topologie est idéale si vous voulez utiliser une batterie Office Web Apps Server dédiée qui est utilisée uniquement par Lync Server 2013.

  - **Utilisation d’un serveur Office Web Apps Server déployé en externe**
    
    Dans cette topologie, Lync Server 2013 est déployé localement et utilise un serveur Office Web Apps Server déployé à l’extérieur de la zone réseau Lync Server. Cela peut se produire lorsque Office Web Apps Server est partagé entre plusieurs applications au sein de l’entreprise et déployé sur un réseau qui exige que Lync Server utilise l’interface externe d’Office Web Apps Server et inversement.
    
    Il n’est pas nécessaire d’installer un serveur proxy inverse ; au lieu de cela, toutes les demandes du serveur Office Web Apps Server vers Lync Server 2013 sont acheminées via votre serveur Edge. Vos clients Lync internes et externes se connectent à Office Web Apps Server à l’aide de l’URL externe.
    
    Si le serveur Office Web Apps Server est déployé à l’extérieur de votre pare-feu interne, sélectionnez l’option le **serveur Office Web Apps Server est déployé sur un réseau externe (périmètre/Internet)** dans le générateur de topologie. Pour plus d’informations, consultez la rubrique Configuration de l' [intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Quelle que soit la topologie que vous sélectionnez, il est essentiel que les ports de pare-feu appropriés soient ouverts. Vous devez vous assurer que les noms DNS, les adresses IP et les ports ne sont pas bloqués par des pare-feu sur le serveur Office Web Apps Server, l’équilibreur de charge ou Lync Server.

<div>


> [!NOTE]  
> Une autre option permettant de fournir un accès externe au serveur Office Web Apps Server consiste à déployer le serveur dans le réseau de périmètre. Si vous choisissez de le faire, gardez à l’esprit que le programme d’installation d’Office Web Apps Server requiert que l’ordinateur serveur soit membre de votre domaine Active Directory. À moins que votre stratégie réseau ne permette aux ordinateurs du réseau de périmètre d’être des membres du domaine Active Directory, il est recommandé de ne pas installer Office Web Apps Server dans le réseau de périmètre. Au lieu de cela, vous devez installer Office Web Apps Server dans le réseau interne et fournir l’accès des utilisateurs externes par le biais de votre serveur proxy inverse.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

