---
title: Composants et topologies utilisés pour les conférences dans Lync Server 2013
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
ms.openlocfilehash: db44e7c8430865fcf8138c9b51f6e700ff85dd7b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a>Composants et topologies utilisés pour les conférences dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-04_

Lorsque vous sélectionnez l’option conférences dans le générateur de topologie, la Conférence est déployée dans le cadre du serveur frontal ou du serveur Standard Edition. Les conférences rendez-vous et le partage PowerPoint nécessitent des composants et une configuration supplémentaires. Les sections suivantes décrivent les composants et topologies pris en charge pour les conférences Web, les conférences A/V et la Conférence rendez-vous.

<div>

## <a name="supported-components"></a>Composants pris en charge

Les seuls composants de conférence Web et de conférence A/V requis sont les serveurs front end de votre organisation ou les serveurs Standard Edition. Pour obtenir la liste des configurations matérielles et logicielles requises pour les serveurs frontaux et les serveurs Standard Edition Server, voir [matériel pris en charge pour Lync server 2013](lync-server-2013-supported-hardware.md) et les [logiciels et les infrastructures du serveur sur Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).

Lync Server 2013 utilise Office Web Apps et Office Web Apps Server pour gérer le partage et le rendu des présentations PowerPoint. Pour plus d’informations sur l’installation et la configuration d’Office Web Apps Server, reportez-vous à la rubrique [configuration de l’intégration avec Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Outre les exigences relatives aux conférences Web et aux conférences audiovisuelles, la Conférence rendez-vous utilise les composants Lync Server 2013 suivants :

  - ****   Le service d’application de service d’application fournit une plate-forme pour le déploiement, l’hébergement et la gestion des applications de communications unifiées. Les conférences rendez-vous utilisent deux applications de communications unifiées qui nécessitent le service d’application : le surveillant de conférences et l’annonce de conférence. Le service d’application est installé et activé par défaut sur chaque serveur frontal d’une grappe frontale et sur tous les serveurs Standard Edition Server lorsque vous déployez une charge de travail de conférence et sélectionnez l’option Conférence rendez-vous.

  - **** L’application attendant du surveillant de conférences est une application de communications unifiées qui accepte les appels de réseau téléphonique commuté (RTC), lit les invites et joint les appels à une conférence a/V.    L’application de surveillance des conférences est installée et activée par défaut lorsque vous déployez une charge de travail de conférence et sélectionnez l’option Conférence rendez-vous.

  - **Annonce**   d’annonce d’annonce d’annonce d’application est une application de communications unifiées qui lit les sons et les invites des participants au RTC sur certaines actions, par exemple lorsque les participants rejoignent ou quittent une conférence, les participants sont en mode muet ou inversement. L’application d’annonce de conférence prend également en charge les commandes de double-tonalité (DTMF) sur le clavier du téléphone. L’application d’annonce de conférences est automatiquement installée et activée par défaut lorsque vous déployez une charge de travail de conférence et sélectionnez l’option Conférence rendez-vous.

  - **Page des paramètres de conférence**   rendez-vous la page des paramètres de conférence rendez-vous affiche les numéros de conférence rendez-vous avec les langues disponibles, les informations sur les conférences téléphoniques affectées (c’est-à-dire pour les réunions dont le planning n’a pas besoin d’être planifié) et les commandes DTMF en conférence, et prend en charge la gestion de votre code confidentiel (pin) et des informations La page des paramètres de conférence rendez-vous est automatiquement installée dans le cadre des services Web.

  - ****   Les conférences rendez-vous de Lync Server 2013, de médiation Server et de passerelle RTC nécessitent un serveur de médiation pour traduire le signalement (et le média, dans certaines configurations) entre Lync Server 2013 et la passerelle RTC et une passerelle PSTN pour traduire les signaux et les médias entre le serveur de médiation et la passerelle RTC. Pour les conférences rendez-vous, vous devez déployer au moins un serveur de médiation et au moins l’un des éléments suivants :
    
      - Passerelle RTC
    
      - IP-PBX
    
      - Contrôleur SBC (Session Border Controller) (pour un fournisseur de services de téléphonie Internet sur lequel vous vous connectez en configurant une jonction SIP [Session Initiation Protocol])
    
    <div>
    

    > [!NOTE]  
    > Si vous déployez également Enterprise Voice, les passerelles RTC et serveur de médiation font partie du déploiement voix entreprise. Si vous ne déployez pas l’entreprise voix, vous devez déployer au moins un serveur de médiation et au moins une passerelle RTC, un PBX IP ou un SBC pour la Conférence rendez-vous.

    
    </div>

  - ****   La Banque de fichiers du magasin de fichiers est utilisée pour les fichiers audio de nom enregistrés. Le magasin de fichiers est un composant standard dans chaque déploiement Entreprise ou Standard.

  - ****   Le magasin utilisateur du Windows Store est utilisé pour stocker les codes confidentiels de Lync Server 2013 des utilisateurs. Les codes confidentiels sont hachés. Le magasin d’utilisateurs est un composant standard dans chaque déploiement Entreprise ou Standard.

  - **Panneau**   de configuration de Lync Server vous pouvez configurer certains paramètres de connexion à l’aide du panneau de configuration de Lync Server.

  - **Lync Server Management Shell**   tous les paramètres de connexion peuvent être configurés à l’aide d’applets de cmdlet Lync Server Management Shell. Les applets de contrôle Lync Server Management Shell sont disponibles pour le déploiement, la configuration, l’exécution, le contrôle et la résolution des problèmes liés à l’application du service de conférence et aux conférences. Pour en savoir plus sur les applets de connexion spécifiques, voir documentation Lync Server Management Shell.

</div>

<div>

## <a name="supported-topologies"></a>Topologies prises en charge

Dans Lync Server 2013, le serveur exécutant Conferencing services est toujours localisé sur les serveurs front-end ou les serveurs Standard Edition. Pendant votre déploiement initial, le générateur de topologie vous donne la possibilité d’inclure des conférences dans votre topologie. Vous pouvez également utiliser le générateur de topologie pour ajouter la fonction de conférence à un déploiement existant. Pour plus d’informations, reportez-vous à [définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

<div>

## <a name="dial-in-conferencing-toplogies"></a>Accès aux conférences Toplogies

Vous pouvez déployer des conférences rendez-vous dans les topologies et configurations suivantes :

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

  - Avec ou sans Voix Entreprise

Vous pouvez déployer une application de service d’application, de surveillant de conférences et d’annonce de conférence dans un site central, mais pas dans un site de filiale.

<div>


> [!NOTE]  
> Si vous déployez la Conférence rendez-vous, vous devez la déployer dans chaque liste où vous déployez Lync Server 2013 Conferencing. Il n’est pas nécessaire d’attribuer des numéros d’accès à chaque pool, mais vous devez déployer la fonctionnalité de conférence rendez-vous dans chaque pool. Cette condition prend en charge la fonctionnalité de nom enregistré quand un utilisateur appelle un numéro d’accès à partir d’un pool pour participer à une conférence 2013 Server Lync dans un autre pool.



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a>Topologies prises en charge pour Lync Server 2013 et Office Web Apps

Lync Server 2013 fournit les méthodes suivantes pour configurer Office Web Apps Server. En fonction de vos besoins, vous pouvez :

  - **Installez Lync Server 2013 et Office Web Apps Server en local derrière le pare-feu de votre organisation, puis dans la même zone réseau.** Avec cette topologie, l’accès externe à Office Web Apps Server sera fourni par le biais de votre serveur proxy inverse. Lync Server 2013 et Office Web Apps Server (ou une batterie de serveurs Office Web Apps) sont installés en local et derrière le pare-feu de votre organisation. Idéalement, vous devez installer Office Web Apps Server dans la même zone réseau que Lync Server.
    
    Les clients Lync externes peuvent se connecter à Lync Server 2013 et à Office Web Apps Server à l’aide d’un serveur de proxy inverse, qui est un serveur qui accepte les requêtes provenant d’Internet et les transmet au réseau interne. (Les clients internes n’ont pas besoin d’utiliser le serveur proxy inverse, car ils peuvent se connecter directement à Office Web Apps Server.) Cette topologie fonctionne de façon optimale si vous souhaitez utiliser une batterie de serveurs Office Web Apps dédiée qui est uniquement utilisée par Lync Server 2013.

  - **Utilisation d’un serveur Office Web Apps déployé en externe**
    
    Dans cette topologie, Lync Server 2013 est déployé en local et utilise un serveur Office Web Apps déployé en dehors de la zone réseau de Lync Server. Cela peut se produire lorsqu’Office Web Apps Server est partagé sur plusieurs applications dans l’entreprise et est déployé sur un réseau nécessitant que Lync Server utilise l’interface externe d’Office Web Apps Server et inversement.
    
    Vous n’avez pas besoin d’installer un serveur proxy inverse ; au lieu de cela, toutes les demandes du serveur Office Web Apps Server vers Lync Server 2013 sont routées via votre serveur Edge. Votre client interne et vos clients Lync externes se connectent à Office Web Apps Server en utilisant l’URL externe.
    
    Si Office Web Apps Server est déployé à l’extérieur de votre pare-feu interne, sélectionnez l’option le **déploiement d’Office Web Apps Server dans un réseau externe (c’est-à-dire le périmètre/Internet)** dans le générateur de topologie. Pour plus d’informations, voir Configuration de l' [intégration à Office Web Apps Server et Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Indépendamment de la topologie sélectionnée, les ports de pare-feu corrects doivent absolument être ouverts. Vous devez vous assurer que les noms DNS, adresses IP et port ne sont pas bloqués par des pare-feu sur le serveur Office Web Apps, l’équilibrage de charge ou le serveur Lync.

<div>


> [!NOTE]  
> Une autre option permettant d’offrir un accès externe à Office Web Apps Server consiste à déployer le serveur dans le réseau de périmètre. Si vous choisissez de le faire, n’oubliez pas que la configuration d’Office Web Apps Server nécessite que l’ordinateur serveur soit membre de votre domaine Active Directory. À moins que votre stratégie réseau autorise la possibilité pour les ordinateurs du réseau périmétrique d’être membres du domaine Active Directory, il est recommandé de ne pas installer le serveur Office Web Apps dans le réseau de périmètre. Au lieu de cela, vous devez installer Office Web Apps Server sur le réseau interne et fournir l’accès des utilisateurs externes par le biais de votre serveur proxy inverse.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

