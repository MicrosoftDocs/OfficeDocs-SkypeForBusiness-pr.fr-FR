---
title: Composants et topologies utilisés pour les conférences dans Lync Server 2013
TOCTitle: Composants et topologies utilisés pour les conférences
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg399061(v=OCS.15)
ms:contentKeyID: 49299221
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Composants et topologies utilisés pour les conférences dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-04_

Lorsque vous sélectionnez la fonctionnalité de conférence dans le Générateur de topologie, celle-ci est déployée comme faisant partie du serveur frontal ou du serveur Standard Edition. La conférence rendez-vous et le partage PowerPoint nécessitent des composants et une configuration supplémentaires. Les sections suivantes décrivent les composants et les topologies pris en charge pour la conférence web, la conférence A/V et la conférence rendez-vous.

## Composants pris en charge

Les seuls composants requis pour la conférence web et la conférence A/V sont les serveurs frontaux ou les serveurs Standard Edition de votre entreprise. Pour obtenir une liste de la configuration logicielle et matérielle requise pour les serveurs frontaux et les serveurs Standard Edition, reportez-vous à [Matériel pris en charge pour Lync Server 2013](lync-server-2013-supported-hardware.md) et [Prise en charge des infrastructures et des logiciels de serveur dans Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).

Lync Server 2013 utilise Office Web Apps et Office Web Apps Server pour gérer le partage et le rendu des présentations PowerPoint. Pour plus d’informations sur l’installation et la configuration d’Office Web Apps Server, reportez-vous à [Configuration de l’intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Outre les conditions requises pour la conférence web et A/V, la conférence rendez-vous utilise les composants Lync Server 2013 suivants :

  - **Service d’application**    service d’application fournit une plateforme pour le déploiement, l’hébergement et la gestion des applications de communications unifiées (UC). La conférence rendez-vous utilise deux applications UC nécessitant le service d’application : Intendant Conférence et le service d’annonce de conférence. Le service d’application est installé et activé par défaut sur chaque serveur frontal d’un pool de serveurs frontaux et sur chaque serveur Standard Edition lorsque vous déployez une charge de travail Conférence et sélectionnez l’option de conférence rendez-vous.

  - **application Intendant Conférence**    application Intendant Conférence est une application de communications unifiées qui accepte les appels réseau téléphonique commuté (RTC), lit les invites, et rassemble les appels vers une conférence A/V. L’application Intendant Conférence est installée et activée par défaut lorsque vous déployez une charge de travail Conférence et sélectionnez l’option de conférence rendez-vous.

  - **application d’annonce de conférence**    application d’annonce de conférenceest une application de communications unifiées qui émet des annonces et des invites aux participants RTC sur certaines actions, comme quand ils joignent ou quittent une conférence, que leur micro est activé ou désactivé, que quelqu’un entre dans la salle d’attente de conférence ou que la conférence est verrouillée ou déverrouillée. L’application d’annonce de conférence prend également en charge les commandes de numérotation en fréquences vocales (DTMF) via le clavier du téléphone. L’application d’annonce de conférence est installée et activée par défaut automatiquement lorsque vous déployez une charge de travail Conférence et sélectionnez l’option de conférence rendez-vous.

  - **page Paramètres de conférence rendez-vous**   La page Paramètres de conférence rendez-vous indique les numéros d’accès aux conférences et les langues dans lesquels ils sont disponibles. Elle présente également les informations relatives aux conférences affectées aux utilisateurs (c’est-à-dire, pour les réunions qui ne doivent pas être planifiées) et comporte des contrôles DTMF à utiliser en cours de conférence. Enfin, elle permet aux utilisateurs de gérer leur code confidentiel et les informations relatives aux conférences qui leur ont été affectées. La page Paramètres de conférence rendez-vous est automatiquement installée dans le cadre du services web.

  - **Lync Server 2013, serveur de médiation et passerelle RTC**   La conférence rendez-vous nécessite un serveur de médiation pour convertir la signalisation (et les médias, dans certaines configurations) entre Lync Server 2013 et la passerelle RTC, ainsi qu’une passerelle RTC pour convertir la signalisation et les médias entre le serveur de médiation et la passerelle RTC. Pour la conférence rendez-vous, vous devez déployer au moins un serveur de médiation et un des éléments suivants :
    
      - Passerelle RTC
    
      - IP-PBX
    
      - Contrôleur de frontière de session (SBC) (pour un fournisseur de services de téléphonie Internet sur lequel vous vous connectez en configurant une jonction SIP)
    
    > [!NOTE]  
    > Si vous déployez également Voix Entreprise, le serveur de médiation et les passerelles RTC font partie du déploiement de Voix Entreprise. Si vous ne déployez pas Voix Entreprise, vous devez déployer au moins un serveur de médiation et une passerelle RTC, un système IP-PBX ou un contrôleur de frontière de session pour la conférence rendez-vous.

  - **Magasin de fichiers**   Le magasin de fichiers est utilisé pour le nom enregistré des fichiers audio. Le magasin de fichiers est un composant standard dans chaque déploiement Enterprise Edition ou Standard Edition.

  - **Magasin d’utilisateurs**   Le magasin d’utilisateurs est utilisé pour stocker les codes confidentiels Lync Server 2013 d’utilisateur. Les codes confidentiels sont hachés. Le magasin d’utilisateurs est un composant standard dans chaque déploiement Enterprise Edition ou Standard Edition.

  - **Panneau de configuration Lync Server**   Certains paramètres de conférence rendez-vous peuvent être configurés à l’aide du Panneau de configuration Lync Server.

  - **Lync Server Management Shell**   Tous les paramètres de conférence rendez-vous peuvent être configurés à l’aide des applets de commande Lync Server Management Shell. Les applets de commande Lync Server Management Shell sont disponibles pour le déploiement, la configuration, l’exécution, la surveillance et la résolution des problèmes de l’application Intendant Conférence et de l’application d’annonce de conférence. Pour plus d’informations sur les applets de commande spécifiques, reportez-vous à la documentation Lync Server Management Shell.

## Topologies prises en charge

Dans Lync Server 2013, le serveur exécutant les services de conférence est toujours colocalisé avec les serveurs frontaux ou les serveurs Standard Edition. Lors de votre déploiement initial, le Générateur de topologie vous donne la possibilité d’inclure la conférence dans votre topologie. Vous pouvez également utiliser le Générateur de topologie pour ajouter la fonction de conférence à un déploiement existant. Pour plus d’informations, reportez-vous à [Définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

## Topologies de conférence rendez-vous

Vous pouvez déployer des conférences rendez-vous dans les topologies et les configurations suivantes :

  - Lync Server 2013Standard Edition

  - Lync Server 2013Enterprise Edition

  - Avec ou sans Voix Entreprise

Vous pouvez déployer le service d’application, l’application Intendant Conférence et l’application d’annonce de conférence dans un site central, mais pas dans un site de succursale.

> [!NOTE]  
> Si vous déployez la conférence rendez-vous, vous devez la déployer dans chaque pool sur lequel vous déployez la conférence Lync Server 2013. Il n’est pas nécessaire d’attribuer des numéros d’accès à chaque pool, mais vous devez déployer la fonctionnalité de conférence rendez-vous dans chaque pool. Cette condition préalable prend en charge la fonctionnalité d’enregistrement du nom lorsqu’un utilisateur appelle un numéro d’accès depuis un pool pour joindre une conférence Lync Server 2013 dans un autre pool.

## Topologies prises en charge pour Lync Server 2013 et Office Web Apps

Lync Server 2013 offre les méthodes de configuration d’Office Web Apps Server suivantes. En fonction de vos besoins, vous pouvez :

  - **installer Lync Server 2013 et Office Web Apps Server localement derrière le pare-feu de votre entreprise et dans la même zone de réseau.** Avec cette topologie, l’accès externe à Office Web Apps Server est fourni via le serveur de proxy inverse. Lync Server 2013 et Office Web Apps Server (ou une batterie de serveurs Office Web Apps Server) sont tous deux installés localement et derrière le pare-feu de votre entreprise. Idéalement, Office Web Apps Server devrait être installé dans la même zone de réseau que Lync Server.
    
    Les clients Lync externes ne peuvent pas se connecter à Lync Server 2013 et à Office Web Apps Server via un serveur de proxy inverse, qui est un serveur qui prend les requêtes sur Internet et les transfère au réseau interne. (Les clients internes n’ont pas besoin d’utiliser le serveur de proxy inverse, car ils peuvent se connecter à Office Web Apps Server directement.) Cette topologie est idéale si vous voulez utiliser une batterie de serveurs Office Web Apps Server dédiée utilisée uniquement par Lync Server 2013.

  - **Using an externally deployed Office Web Apps Server**
    
    Dans cette topologie, Lync Server 2013 est déployé localement et utilise Office Web Apps Server, qui est déployé en dehors de la zone de réseau de Lync Server. Cela peut se produire lorsqu’Office Web Apps Server est partagé sur plusieurs applications dans l’entreprise et qu’il est déployé dans un réseau nécessitant Lync Server pour utiliser l’interface externe d’Office Web Apps Server, et inversement.
    
    Il n’est pas nécessaire d’installer un serveur de proxy inverse. À la place, toutes les requêtes d’Office Web Apps Server vers Lync Server 2013 sont acheminées à travers votre serveur Edge. Vos clients Lync internes et externes se connectent à Office Web Apps Server à l’aide de l’URL externe.
    
    Si Office Web Apps Server est déployé en dehors de votre pare-feu interne, sélectionnez l’option **Office Web Apps Server est déployé dans un réseau externe (c’est-à-dire, périmètre/Internet)** dans le Générateur de topologie. Pour plus d’informations, reportez-vous à [Configuration de l’intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Indépendamment de la topologie sélectionnée, les ports de pare-feu corrects doivent absolument être ouverts. Vous devez vous assurer que les noms DNS, adresses IP et ports ne sont pas bloqués par des pare-feu sur Office Web Apps Server, le programme d’équilibrage de la charge ou Lync Server.

> [!NOTE]  
> Une autre option permettant de fournir un accès externe à Office Web Apps Server consiste à déployer le serveur dans le réseau de périmètre. Si vous sélectionnez cette option, n’oubliez pas que pour installer Office Web Apps Server, l’ordinateur serveur doit être membre de votre domaine Active Directory. À moins que votre stratégie de réseau n’autorise les ordinateurs du réseau de périmètre à être des membres du domaine Active Directory, il est recommandé de ne pas installer Office Web Apps Server dans le réseau de périmètre. Installez plutôt Office Web Apps Server dans le réseau interne et fournissez un accès utilisateur externe via votre serveur de proxy inverse.
