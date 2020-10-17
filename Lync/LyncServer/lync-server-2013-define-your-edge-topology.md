---
title: 'Lync Server 2013 : définition de votre topologie Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceba1f397493ac0ef6961099877643f802c11d93
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504561"
---
# <a name="define-your-edge-topology-in-lync-server-2013"></a>Définition de votre topologie Edge dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Vous devez utiliser le générateur de topologie pour créer votre topologie et vous devez configurer au moins un pool frontal interne ou un serveur Standard Edition Server avant de déployer votre serveur Edge. Utilisez la procédure suivante pour définir la topologie Edge pour un serveur Edge unique, puis utilisez les procédures de la page [publier votre topologie dans Lync server 2013](lync-server-2013-publish-your-topology.md) et [exporter votre topologie Lync Server 2013, puis copiez-la dans le support externe pour l’installation Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) pour publier la topologie et la mettre à la disposition de votre serveur Edge.

<div>


> [!NOTE]  
> Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge.



</div>

Pour réussir à publier, activer ou désactiver une topologie lorsque vous ajoutez ou supprimez un rôle serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Administrateurs du domaine. Il est également possible de déléguer les droits et autorisations d’administrateur appropriés pour ajouter des rôles serveur à un compte d'utilisateur. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) dans la documentation de déploiement du serveur Standard Edition Server ou Enterprise Edition. Pour toutes les autres modifications de configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est requise.

Si vous avez défini votre topologie de serveur Edge lorsque vous avez défini et publié votre topologie interne et qu’aucune modification n’est requise pour la topologie Edge que vous avez définie précédemment, vous n’avez pas besoin de la définir et de la publier à nouveau. Utilisez la procédure suivante uniquement si vous devez modifier votre topologie Edge. Vous devez définir la topologie précédemment définie et publiée comme étant disponible pour vos serveurs Edge, comme vous le faites à l’aide de la procédure décrite dans [Export Your Lync Server 2013 Topology et copy it to External Media for Edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

<div>


> [!IMPORTANT]  
> Vous ne pouvez pas exécuter le générateur de topologie à partir d’un serveur Edge. Vous devez l’exécuter à partir de votre serveur frontal ou de vos serveurs Standard Edition.



</div>

Le processus de définition de la topologie de serveur Edge s’effectuera dans le générateur de topologie. Les trois principaux types de topologies de serveurs Edge que vous pouvez planifier et configurer sont répertoriés ci-dessous :

  - Pour définir la topologie pour un serveur Edge unique

  - Pour définir la topologie pour un pool de serveurs Edge à charge équilibrée

  - Pour définir la topologie pour un pool de serveurs Edge à charge matérielle équilibrée

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a>Pour définir la topologie pour un serveur Edge unique

1.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.

2.  Dans l’arborescence de la console, développez le site dans lequel vous souhaitez déployer un serveur Edge.

3.  Cliquez avec le bouton droit sur **Pools**de serveurs Edge, puis cliquez sur **nouveau pool**de serveurs Edge.

4.  Dans **Définir le nouveau pool Edge**, cliquez sur **Suivant**.

5.  Dans **Définir le nom de domaine complet du pool Edge**, procédez comme suit :
    
      - Dans **Nom de domaine complet du pool**, tapez le nom de domaine complet (FQDN) de l’interface interne pour le serveur Edge.
        
        <div>
        

        > [!IMPORTANT]  
        > Le nom que vous spécifiez doit être identique au nom de l’ordinateur configuré sur le serveur. Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, pas un nom de domaine complet (FQDN). Le Générateur de topologies utilise des noms de domaine complets (FQDN), non des noms courts. Vous devez donc configurer un suffixe DNS sur le nom de l’ordinateur à déployer en tant que serveur Edge non joint à un domaine. Utilisez uniquement des caractères standard (A à Z, a à z, 0 à 9 et tirets) lorsque vous affectez des noms de domaine complets à vos serveurs Lync, serveurs Edge et pools. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard dans les noms de domaine complets ne sont souvent pas pris en charge par les DNS externes et les autorités de certification publiques (lorsque le nom de domaine complet doit être affecté à l’élément SN (nom du sujet) du certificat). Pour plus d’informations sur l’ajout d’un suffixe DNS à un nom d’ordinateur, voir <A href="lync-server-2013-configure-dns-for-edge-support.md">configure DNS for Edge support in Lync Server 2013</A>.

        
        </div>
    
      - Cliquez sur **Pool d’un seul ordinateur**, puis sur **Suivant**.

6.  Dans **Sélectionner les fonctionnalités**, procédez comme suit :
    
      - Si vous envisagez d’utiliser un seul nom de domaine complet et une seule adresse IP pour le service d’accès SIP, le service de conférence Web Lync Server 2013 et les services Edge A/V, activez la case à cocher **utiliser un seul nom de domaine complet et une seule adresse IP** .
    
      - Si vous envisagez d’activer la fédération, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**.
        
        <div>
        

        > [!NOTE]  
        > Vous pouvez activer cette option, mais un seul pool de serveurs Edge ou serveur Edge dans votre organisation peut être publié en externe pour la fédération. Tout accès par des utilisateurs fédérés, notamment les utilisateurs de messagerie instantanée publique, passe par le même pool de serveurs Edge ou serveur Edge unique. Par exemple, si votre déploiement inclut un pool de serveurs Edge ou un serveur Edge unique déployé à New York et un déployé à Londres et que vous activez la prise en charge de la fédération sur le pool de serveurs Edge ou le serveur Edge unique de New York, le trafic de signalisation des utilisateurs fédérés passera par le pool de serveurs Edge ou le serveur Edge unique de New York. Ceci s’applique aussi aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le pool de serveurs ou le serveur Edge de Londres pour le trafic A/V.

        
        </div>
    
      - Si vous envisagez de prendre en charge le protocole XMPP (Extensible Messaging and Presence Protocol) pour votre déploiement, activez la case à cocher **Activer la fédération XMPP (port 5269)**

7.  Dans **Sélectionner les options IP**, procédez comme suit :
    
      - **Activer IPv4 sur l’interface interne**: activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool de serveurs Edge
    
      - **Activer IPv6 sur l’interface interne**: activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool de serveurs Edge
    
      - **Activer IPv4 sur l’interface externe**: activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool de serveurs Edge
    
      - **Activer IPv6 sur l’interface externe**: activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool de serveurs Edge
    
    Vous pouvez également configurer le serveur Edge ou le pool de serveurs Edge pour utiliser une adresse de traduction d’adresses réseau pour les adresses IP externes. Pour ce faire, activez la case à cocher **L’adresse IP externe de ce pool Edge est traduite par NAT**.

8.  Dans **Noms de domaine complets externes**, procédez comme suit :
    
      - Si dans **Sélectionner les fonctionnalités** vous envisagez d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez le nom de domaine complet externe dans **Accès SIP**.
        
        <div>
        

        > [!NOTE]  
        > Si vous sélectionnez cette option, vous devez spécifier un numéro de port différent pour chacun des services Edge (paramètres de port recommandés : 5061 pour le service Edge d’accès, 444 pour le service Edge de conférence web et 443 pour le service Edge A/V). L’activation de cette option permet d’éviter les problèmes de connectivité potentiels et de simplifier la configuration, car vous pouvez alors utiliser le même numéro de port (par exemple 443) pour les trois services.

        
        </div>
    
      - Si dans **Sélectionner les fonctionnalités** vous n’avez pas choisi d’utiliser un seul nom de domaine complet et une seule adresse IP, tapez les noms de domaine complets pour les services **Accès SIP**, **Conférence web** et **Audio Vidéo**, en conservant les ports par défaut.

9.  Cliquez sur **Suivant**.

10. Dans **Définir l’adresse IP interne**, tapez l’adresse IP de votre serveur Edge dans **Adresse IPv4 interne** et **Adresse IPv6 interne** selon votre configuration. Cliquez sur **Suivant**.

11. Dans **Définir l’adresse IP externe**, procédez comme suit :
    
      - Si vous avez décidé d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez l’adresse IPv4 externe du serveur Edge dans **Accès SIP**, puis cliquez sur **Suivant**.
    
      - Si vous avez choisi d’utiliser des adresses IPv6, tapez l’adresse IPv6 externe du serveur Edge dans **Accès SIP**, puis cliquez sur **Suivant**.
    
      - Si vous n’avez pas choisi d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez les adresses IPv4 externes du serveur Edge dans **Accès SIP**, **Conférence web** et **Conférence A/V**, puis cliquez sur **Suivant**.
    
      - Si vous avez choisi d’utiliser des adresses IPv6 et de ne pas utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez les adresses IPv6 externes du serveur Edge dans **Accès SIP**, **Conférence web** et **Conférence A/V**, puis cliquez sur **Suivant**.
        
        <div>
        

        > [!NOTE]  
        > Si vous n’avez pas activé l’utilisation d’adresses IPv6, cette boîte de dialogue ne s’affiche pas.

        
        </div>

12. Si vous avez choisi d’utiliser la traduction d’adresses réseau (NAT), une boîte de dialogue s’affiche. Dans **Adresse IPv4 publique pour le service Edge A/V**, tapez l’adresse IPv4 publique à traduire par NAT, puis cliquez sur **Suivant**.
    
    <div>
    

    > [!NOTE]  
    > Il doit s’agir de l’adresse IP externe du service Edge A/V.

    
    </div>

13. Si vous avez choisi d’utiliser la traduction d’adresses réseau (NAT) et des adresses IPv6, une boîte de dialogue s’affiche. Dans **Adresse IPv6 publique pour le service Edge A/V**, tapez l’adresse IPv6 publique à traduire par NAT, puis cliquez sur **Suivant**.
    
    <div>
    

    > [!NOTE]  
    > Il doit s’agir de l’adresse IP externe du service Edge A/V.

    
    </div>

14. Dans **Définir le tronçon suivant**, dans la zone **Pool du tronçon suivant**, sélectionnez le nom du pool interne qui peut être soit un pool frontal, soit un pool de serveurs Standard Edition. Ou, si votre déploiement inclut un directeur, sélectionnez-le, puis cliquez sur **Suivant**.

15. Dans **Pools frontaux associés**, spécifiez un ou plusieurs pools internes à associer à ce serveur Edge, notamment des pools frontaux et des serveurs Standard Edition Server, en sélectionnant les noms des pools internes qui utiliseront ce serveur Edge pour communiquer avec les utilisateurs externes pris en charge.
    
    <div>
    

    > [!NOTE]  
    > Un seul pool de serveurs Edge avec charge équilibrée ou serveur Edge unique peut être associé à chaque pool interne pour le trafic A/V. Si vous avez déjà un pool interne associé à un pool de serveurs Edge ou à un serveur Edge unique, un avertissement apparaît vous indiquant que le pool interne est déjà associé à un pool de serveurs Edge ou à un serveur Edge unique. Si vous sélectionnez un pool qui est déjà associé à un autre serveur Edge, cela modifiera l’association.

    
    </div>

16. Cliquez sur **Terminer**.

17. Publiez votre topologie.

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Pour définir la topologie pour un pool de serveurs Edge avec charge DNS équilibrée

1.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.

2.  Dans l’arborescence de la console, développez le site dans lequel vous souhaitez déployer les serveurs Edge.

3.  Cliquez avec le bouton droit sur **Pools de serveurs Edge**, puis cliquez sur **Nouveau pool de serveurs Edge**.

4.  Dans **Définir le nouveau pool Edge**, cliquez sur **Suivant**.

5.  Dans **Définir le nom de domaine complet du pool Edge**, procédez comme suit :
    
      - Dans **Nom de domaine complet du pool**, tapez le nom de domaine complet (FQDN) pour la connexion interne du pool de serveurs Edge.
        
        <div>
        

        > [!IMPORTANT]  
        > Le nom de pool que vous indiquez doit être identique au nom du pool Edge interne. Il doit être défini comme nom de domaine complet (FQDN). Le Générateur de topologies utilise des noms de domaine complets (FQDN), non des noms courts. Utilisez uniquement des caractères standard (A à Z, a à z, 0 à 9 et tirets) lorsque vous affectez des noms de domaine complets à vos serveurs Lync, serveurs Edge et pools. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard dans les noms de domaine complets ne sont souvent pas pris en charge par les DNS externes et les autorités publiques de certification (lorsque le nom de domaine complet doit être affecté à l’élément SN (nom de sujet) du certificat).

        
        </div>
    
      - Cliquez sur **Pool de plusieurs ordinateurs**, puis sur **Suivant**.

6.  Dans **Sélectionner les fonctionnalités**, procédez comme suit :
    
      - Si vous envisagez d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence Web Lync Server 2013 et les services Edge A/V, activez la case à cocher **utiliser un seul nom de domaine complet et une seule adresse IP** .
    
      - Si vous envisagez d’activer la fédération, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**. Cliquez sur **Suivant**
        
        <div>
        

        > [!NOTE]  
        > Vous pouvez activer cette option, mais un seul pool de serveurs Edge ou serveur Edge dans votre organisation peut être publié en externe pour la fédération. Tout accès par des utilisateurs fédérés, notamment les utilisateurs de messagerie instantanée publique, passe par le même pool de serveurs Edge ou serveur Edge unique. Par exemple, si votre déploiement inclut un pool de serveurs Edge ou un serveur Edge unique déployé à New York et un déployé à Londres et que vous activez la prise en charge de la fédération sur le pool de serveurs Edge ou le serveur Edge unique de New York, le trafic de signalisation des utilisateurs fédérés passera par le pool de serveurs Edge ou le serveur Edge unique de New York. Ceci s’applique aussi aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le pool de serveurs ou le serveur Edge de Londres pour le trafic A/V.

        
        </div>
    
      - Si vous envisagez de prendre en charge le protocole XMPP (Extensible Messaging and Presence Protocol) pour votre déploiement, activez la case à cocher **Activer la fédération XMPP (port 5269)**

7.  Cliquez sur **Suivant**.

8.  Dans **Sélectionner les options IP**, procédez comme suit :
    
      - **Activer IPv4 sur l’interface interne**: activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool de serveurs Edge
    
      - **Activer IPv6 sur l’interface interne**: activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool de serveurs Edge
    
      - **Activer IPv4 sur l’interface externe**: activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool de serveurs Edge
    
      - **Activer IPv6 sur l’interface externe**: activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool de serveurs Edge
    
    Vous pouvez également configurer le serveur Edge ou le pool de serveurs Edge pour utiliser une adresse de traduction d’adresses réseau pour les adresses IP externes. Pour ce faire, activez la case à cocher **L’adresse IP externe de ce pool Edge est traduite par NAT**.

9.  Dans **Noms de domaine complets externes**, procédez comme suit :
    
      - Si, dans **Sélectionner les fonctionnalités**, vous avez choisi d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez le nom de domaine complet externe dans **Accès SIP**.
        
        <div>
        

        > [!NOTE]  
        > Si vous sélectionnez cette option, vous devez spécifier un numéro de port différent pour chacun des services Edge (paramètres de port recommandés : 5061 pour le service Edge d’accès, 444 pour le service Edge de conférence web et 443 pour le service Edge A/V). L’activation de cette option permet d’éviter les problèmes de connectivité potentiels et de simplifier la configuration, car vous pouvez alors utiliser le même numéro de port (par exemple 443) pour les trois services.

        
        </div>
    
      - Si, dans **Sélectionner les fonctionnalités**, vous n’avez pas décidé d’utiliser un seul nom de domaine complet et une seule adresse IP, tapez le nom de domaine complet que vous avez choisi pour le côté accessible au public du pool de serveurs Edge dans **Accès SIP**. Dans **Conférence web**, tapez le nom de domaine complet que vous avez choisi pour le côté accessible au public du pool de serveurs Edge. Dans **Audio/Vidéo**, tapez le nom de domaine complet que vous avez choisi pour le côté accessible au public du pool de serveurs Edge. Utilisez les ports par défaut.

10. Cliquez sur **Suivant**.

11. Dans **Définissez les ordinateurs inclus dans ce pool**, cliquez sur **Ajouter**.

12. Dans **FQDN et adresse IP internes**, procédez comme suit :
    
      - Dans **Adresse IPv4 interne**, tapez l’adresse IPv4 et l’**Adresse IPv6 interne** selon les besoins du premier serveur Edge à créer dans ce pool.
    
      - Dans **Nom de domaine complet (FQDN) interne**, tapez le nom de domaine complet du premier serveur Edge que vous souhaitez créer dans ce pool.
        
        <div>
        

        > [!NOTE]  
        > Le nom que vous spécifiez doit être identique au nom de l’ordinateur configuré sur le serveur. Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, non un nom de domaine complet. Le Générateur de topologies utilise des noms de domaine complets (FQDN), non des noms courts. Vous devez donc configurer un suffixe DNS sur le nom de l’ordinateur à déployer en tant que serveur Edge non joint à un domaine. Utilisez uniquement des caractères standard (A à Z, a à z, 0 à 9 et tirets) lorsque vous affectez des noms de domaine complets à vos serveurs Lync, serveurs Edge, pools et tableaux. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard dans les noms de domaine complets ne sont souvent pas pris en charge par les DNS externes et les autorités de certification publiques (lorsque le nom de domaine complet doit être affecté à l’élément SN (nom du sujet) du certificat). Pour plus d’informations sur l’ajout d’un suffixe DNS à un nom d’ordinateur, voir <A href="lync-server-2013-configure-dns-for-edge-support.md">configure DNS for Edge support in Lync Server 2013</A>.

        
        </div>

13. Cliquez sur **Suivant**.

14. Dans **Définir les adresses IP externes**, procédez comme suit :
    
      - Si vous décidez d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence Web et le service Edge A/V, tapez l’adresse IP externe du serveur Edge dans **Accès SIP**.
    
      - Si vous avez décidé de ne pas utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service de conférence A/V, tapez l’adresse IP que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge dans **Accès SIP**. Dans **Conférence web**, tapez l’adresse IP que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge. Dans **Conférence A/V**, tapez l’adresse IP que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge.

15. Cliquez sur **Suivant**.

16. Si vous avez activé l’utilisation des adresses IPv6, dans **Définir l’adresse IP externe**, procédez comme suit :
    
      - Si vous avez décidé d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez l’adresse IPv6 externe du serveur Edge dans **Accès SIP**.
    
      - Si vous avez décidé de ne pas utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service de conférence A/V, tapez l’adresse IPv6 que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge dans **Accès SIP**. Dans **Conférence web**, tapez l’adresse IPv6 que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge. Dans **Conférence A/V**, tapez l’adresse IPv6 que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge.
    
    <div>
    

    > [!NOTE]  
    > Si vous n’avez pas activé l’utilisation d’adresses IPv6, cette boîte de dialogue ne s’affiche pas.

    
    </div>

17. Cliquez sur **Terminer**.
    
    <div>
    

    > [!NOTE]  
    > Le premier serveur Edge créé dans votre pool apparaît maintenant dans la boîte de dialogue <STRONG>Définissez les ordinateurs inclus dans ce pool</STRONG>.

    
    </div>

18. Dans **Définissez les ordinateurs inclus dans ce pool**, cliquez sur **Ajouter**, puis répétez les étapes 11 à 14 pour le deuxième serveur Edge à ajouter à votre pool de serveurs Edge.

19. Après avoir exécuté les étapes 11 à 14, cliquez sur **Suivant** dans **Définissez les ordinateurs inclus dans ce pool**.
    
    <div>
    

    > [!NOTE]  
    > À ce stade, les deux serveurs Edge sont visibles dans le pool.

    
    </div>

20. Si vous avez choisi d’utiliser la traduction d’adresses réseau (NAT), une boîte de dialogue s’affiche. Dans **Adresse IP publique**, tapez les adresses IPv4 et IPv6 (le cas échéant) publiques à traduire par NAT, puis cliquez sur **Suivant**.
    
    <div>
    

    > [!NOTE]  
    > Il doit s’agir de l’adresse IP externe du service Edge A/V.

    
    </div>

21. Dans **Définir le tronçon suivant**, dans la liste **Pool du tronçon suivant**, sélectionnez le nom du pool interne qui peut être soit un pool de serveurs frontaux, soit un pool de serveurs Standard Edition Server. Ou, si votre déploiement inclut un directeur, sélectionnez son nom. Cliquez ensuite sur **Suivant**.

22. Dans **Pools frontaux associés**, spécifiez un ou plusieurs pools internes à associer à ce serveur Edge, notamment des pools frontaux et des serveurs Standard Edition Server, en sélectionnant les noms des pools internes qui utiliseront ce serveur Edge pour communiquer avec les utilisateurs externes pris en charge.
    
    <div>
    

    > [!NOTE]  
    > Un seul pool de serveurs Edge avec charge équilibrée ou serveur Edge unique peut être associé à chaque pool interne pour le trafic A/V. Si vous avez déjà un pool interne associé à un pool de serveurs Edge ou à un serveur Edge unique, un avertissement apparaît vous indiquant que le pool interne est déjà associé à un pool de serveurs Edge ou à un serveur Edge unique. Si vous sélectionnez un pool qui est déjà associé à un autre serveur Edge, cela modifiera l’association.

    
    </div>

23. Cliquez sur **Terminer**.

24. Publiez votre topologie.

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Pour définir la topologie pour un pool de serveurs Edge à charge matérielle équilibrée

1.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.

2.  Dans l’arborescence de la console, développez le site dans lequel vous souhaitez déployer les serveurs Edge.

3.  Cliquez avec le bouton droit sur **Pools**de serveurs Edge, puis sélectionnez **nouveau pool de serveurs Edge**.

4.  Dans **Définir le nouveau pool Edge**, cliquez sur **Suivant**.

5.  Dans **Définir le nom de domaine complet du pool Edge**, procédez comme suit :
    
      - Dans **Nom de domaine complet**, tapez le nom de domaine complet (FQDN) de l’interface interne pour le pool de serveurs Edge.
        
        <div>
        

        > [!IMPORTANT]  
        > Le nom de pool que vous indiquez doit être identique au nom du pool Edge interne. Il doit être défini comme nom de domaine complet (FQDN). Le Générateur de topologies utilise des noms de domaine complets (FQDN), non des noms courts. Utilisez uniquement des caractères standard (A à Z, a à z, 0 à 9 et tirets) lorsque vous affectez des noms de domaine complets à vos serveurs Lync, serveurs Edge et pools. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard dans les noms de domaine complets ne sont souvent pas pris en charge par les DNS externes et les autorités de certification publiques (lorsque le nom de domaine complet doit être affecté à l’élément SN (nom du sujet) du certificat).

        
        </div>
    
    <!-- end list -->
    
      - Cliquez sur **pool de plusieurs ordinateurs**, puis sur **suivant**.

6.  Dans **Sélectionner les fonctionnalités**, procédez comme suit :
    
      - Si vous envisagez d’utiliser un seul nom de domaine complet et une seule adresse IP pour le service d’accès SIP, le service de conférence Web Lync Server et le service Edge A/V, activez la case à cocher **utiliser un seul nom de domaine complet & adresse IP** .
    
      - Si vous envisagez d’activer la fédération, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**.
        
        <div>
        

        > [!NOTE]  
        > Vous pouvez activer cette option, mais un seul pool Edge ou serveur Edge dans votre organisation peut être publié en externe pour la fédération. Tout accès par des utilisateurs fédérés, notamment les utilisateurs de messagerie instantanée publique, passe par le même pool de serveurs Edge ou serveur Edge unique. Par exemple, si votre déploiement comprend un pool de serveurs Edge ou un serveur Edge unique déployé à New York, et un autre déployé à Londres, et que vous activez la prise en charge de fédération sur le pool de serveurs Edge ou serveur Edge unique de New York, le trafic de signalisation pour les utilisateurs fédérés passera par le pool de serveurs Edge ou serveur Edge unique de New York. Ceci s’applique aussi aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le pool de serveurs ou le serveur Edge de Londres pour le trafic A/V.

        
        </div>
    
      - Si vous envisagez de prendre en charge le protocole XMPP (Extensible Messaging and Presence Protocol) pour votre déploiement, activez la case à cocher **Activer la fédération XMPP (port 5269)**

7.  Cliquez sur **Suivant**.

8.  Dans **Sélectionner les options IP**, procédez comme suit :
    
      - **Activer IPv4 sur l’interface interne**: activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool de serveurs Edge
    
      - **Activer IPv6 sur l’interface interne**: activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool de serveurs Edge
    
      - **Activer IPv4 sur l’interface externe**: activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool de serveurs Edge
    
      - **Activer IPv6 sur l’interface externe**: activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool de serveurs Edge
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>N’activez pas</STRONG> la case à cocher <STRONG>L’adresse IP externe de ce pool de serveurs Edge est traduite par NAT</STRONG>. La traduction d’adresses réseau (NAT) n’est pas prise en charge lorsque vous utilisez l’équilibrage de la charge matérielle.

    
    </div>

9.  Dans **Noms de domaine complets externes**, procédez comme suit :
    
      - Si, dans **Sélectionner les fonctionnalités**, vous avez choisi d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez le nom de domaine complet externe dans **Accès SIP**.
        
        <div>
        

        > [!NOTE]  
        > Si vous décidez d’activer cette option, vous devez spécifier un numéro de port différent pour chacun des services Edge (paramètres de port recommandés : 5061 pour le service Edge d’accès, 444 pour le service Edge de conférence web et 443 pour le service Edge A/V). L’activation de cette option permet d’éviter les problèmes de connectivité potentiels et de simplifier la configuration, car vous pouvez alors utiliser le même numéro de port (par exemple 443) pour les trois services.

        
        </div>
    
      - Si, dans **Sélectionner les fonctionnalités**, vous n’avez pas décidé d’utiliser un seul nom de domaine complet et une seule adresse IP, tapez le nom de domaine complet que vous avez choisi pour le côté accessible au public du pool de serveurs Edge dans **Accès SIP**. Dans **Conférence web**, tapez le nom de domaine complet que vous avez choisi pour le côté accessible au public du pool de serveurs Edge. Dans **Audio/Vidéo**, tapez le nom de domaine complet que vous avez choisi pour le côté accessible au public du pool de serveurs Edge. Utilisez les ports par défaut.
        
        <div>
        

        > [!NOTE]  
        > Il serviront de noms de domaine complets des adresses IP virtuelles (VIP) accessibles au public.

        
        </div>

10. Cliquez sur **Suivant**.

11. Dans **Définissez les ordinateurs inclus dans ce pool**, cliquez sur **Ajouter**.

12. Dans **Définir les adresses IP externes**, procédez comme suit :
    
      - Si vous avez décidé d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez l’adresse IPv4 externe du serveur Edge dans **Accès****SIP**.
    
      - Si vous avez décidé de ne pas utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service de conférence A/V, tapez l’adresse IP que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge dans **Accès SIP**. Dans **Conférence web**, tapez l’adresse IP que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge. Dans **Conférence A/V**, tapez l’adresse IP que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge.

13. Cliquez sur **Suivant**.

14. Si vous avez activé l’utilisation des adresses IPv6, dans **Définir l’adresse IP externe**, procédez comme suit :
    
      - Si vous avez décidé d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez l’adresse IPv6 externe du serveur Edge dans **Accès SIP**.
    
      - Si vous avez décidé de ne pas utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service de conférence A/V, tapez l’adresse IPv6 que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge dans **Accès SIP**. Dans **Conférence web**, tapez l’adresse IPv6 que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge. Dans **Conférence A/V**, tapez l’adresse IPv6 que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge.
    
    <div>
    

    > [!NOTE]  
    > Si vous n’avez pas activé l’utilisation d’adresses IPv6, cette boîte de dialogue ne s’affiche pas.

    
    </div>

15. Cliquez sur **Terminer**.
    
    <div>
    

    > [!NOTE]  
    > Le premier serveur Edge créé dans votre pool apparaît maintenant dans la boîte de dialogue <STRONG>Définissez les ordinateurs inclus dans ce pool</STRONG>.

    
    </div>

16. Dans **Définissez les ordinateurs inclus dans ce pool**, cliquez sur **Ajouter**, puis répétez les étapes 11 à 14 pour le deuxième serveur Edge que vous souhaitez ajouter à votre pool de serveurs Edge.

17. Après avoir exécuté les étapes 11 à 14, cliquez sur **Suivant** dans **Définissez les ordinateurs inclus dans ce pool**.
    
    <div>
    

    > [!NOTE]  
    > À ce stade, les deux serveurs Edge sont visibles dans le pool.

    
    </div>

18. Dans **Définir le tronçon suivant**, dans la liste **Pool du tronçon suivant**, sélectionnez le nom du pool interne qui peut être soit un pool de serveurs frontaux, soit un pool de serveurs Standard Edition Server. Ou, si votre déploiement inclut un directeur, sélectionnez son nom. Cliquez ensuite sur **Suivant**.

19. Dans **Pools frontaux associés**, spécifiez un ou plusieurs pools internes à associer à ce serveur Edge, notamment des pools frontaux et des serveurs Standard Edition Server, en sélectionnant les noms des pools internes qui utiliseront ce serveur Edge pour communiquer avec les utilisateurs externes pris en charge.
    
    <div>
    

    > [!NOTE]  
    > Un seul pool de serveurs Edge avec charge équilibrée ou serveur Edge unique peut être associé à chaque pool interne pour le trafic A/V. Si vous avez déjà un pool interne associé à un pool de serveurs Edge ou à un serveur Edge unique, un avertissement apparaît vous indiquant que le pool interne est déjà associé à un pool de serveurs Edge ou à un serveur Edge unique. Si vous sélectionnez un pool qui est déjà associé à un autre serveur Edge, cela modifiera l’association.

    
    </div>

20. Cliquez sur **Terminer**.

21. Publiez votre topologie.

</div>

</div>

<span> </span>

</div>

</div>

</div>

