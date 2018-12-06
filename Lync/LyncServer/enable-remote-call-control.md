---
title: Activation du contrôle d’appel distant
TOCTitle: Activation du contrôle d’appel distant
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204664(v=OCS.15)
ms:contentKeyID: 49296213
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation du contrôle d’appel distant

 

_**Dernière rubrique modifiée :** 2012-10-02_

Le contrôle d’appel distant permet aux utilisateurs de contrôler leurs téléphones de bureau PBX (autocommutateur privé) à l’aide de Lync Server 2013. Si vous avez déployé le contrôle d’appel distant dans votre environnement hérité et souhaitez le faire migrer vers Lync Server 2013, vous devez effectuer les tâches suivantes :

1.  Installez une passerelle SIP/CSTA et configurez-la afin de communiquer avec votre système PBX. Vous devez effectuer cette étape lorsque vous déployez votre pool pilote Lync Server 2013.

2.  Une fois que vous avez fusionné votre topologie et fait migrer vos stratégies et paramètres, configurez Lync Server 2013 afin d’acheminer les requêtes CSTA vers la passerelle SIP/CSTA. Cette étape est une étape manuelle qui suit la migration automatisée. Pour configurer l’acheminement des requêtes CSTA, procédez comme suit :
    
      - Supprimez les entrées d’hôtes autorisés héritées (appelées *entrées de serveur approuvé* dans Lync Server 2013). Si vous faites migrer les utilisateurs depuis votre déploiement hérité, veillez à supprimer toutes les entrées d’hôtes autorisés existantes que vous avez créées pour la passerelle SIP/CSTA avant de configurer de nouvelles entrées d’application approuvée sur le pool pilote Lync Server 2013. Pour plus d’informations sur la manière de supprimer les entrées d’hôtes autorisés héritées, consultez [Suppression d’une entrée hôte non autorisée](remove-an-authorized-host-entry.md).
    
      - Configurez un itinéraire statique pour le contrôle d’appel distant. Vous pouvez configurer un itinéraire statique pour les pools individuels qui prendront en charge le contrôle d’appel distant, ou vous pouvez configurer un itinéraire statique global afin que chaque pool qui n’est pas configuré avec un itinéraire statique utilise l’itinéraire statique global. Pour plus d’informations sur la manière de configurer l’itinéraire statique, reportez-vous à [Configuration d’un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) dans la documentation de déploiement.
    
      - Configurez une entrée d’application approuvée pour le contrôle d’appel distant sur chaque pool qui prendra en charge le contrôle d’appel distant. Pour plus d’informations sur la façon de configurer une entrée d’application approuvée, reportez-vous à [Configuration d’une entrée d’application approuvée pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) dans la documentation de déploiement.

3.  Si vous avez déployé une passerelle SIP/CSTA qui utilise le protocole TCP (Transmission Control Protocol) pour se connecter à Lync Server 2013, définissez l’adresse IP de la passerelle dans le générateur de topologie. Pour plus d’informations sur la définition de l’adresse IP, reportez-vous à [Définition d’une adresse IP de passerelle SIP/CSTA dans Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) dans la documentation de déploiement.

4.  Configurez les utilisateurs Lync 2013 pour le contrôle d’appel distant en activant ce dernier et en affectant un URI (Uniform Resource Identifier) de serveur de ligne et un URI de ligne. Lorsque vous faites migrer des utilisateurs depuis votre déploiement hérité vers Lync Server 2013, les paramètres du contrôle d’appel distant migrent avec les autres paramètres d’utilisateur.

5.  Si vous avez personnalisé les règles de normalisation des numéros de téléphone du carnet d’adresses dans votre déploiement hérité, vous devez effectuer certaines tâches manuelles une fois que la migration automatisée des stratégies et paramètres est terminée afin de faire migrer ces règles de normalisation personnalisées. Si vous n’avez pas personnalisé les règles de normalisation, le carnet d’adresses migre avec le reste de votre topologie. Pour plus d’informations sur la migration manuelle des règles de normalisation personnalisées, reportez-vous à [Migration du carnet d’adresses](migrate-address-book_1.md).

