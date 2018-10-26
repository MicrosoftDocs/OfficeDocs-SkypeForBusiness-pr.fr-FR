---
title: 'Lync Server 2013 : Définition de la topologie Edge'
TOCTitle: Définition de la topologie Edge
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398591(v=OCS.15)
ms:contentKeyID: 49297784
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition de la topologie Edge dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-28_

Vous devez utiliser le Générateur de topologie pour créer votre topologie, et vous devez configurer au moins un pool frontal ou serveur Standard Edition interne avant de pouvoir déployer votre serveur Edge. Utilisez la procédure suivante pour définir la topologie Edge pour un serveur Edge unique, puis utilisez les procédures décrites dans [Publication de la topologie dans Lync Server 2013](lync-server-2013-publish-your-topology.md) et [Exportation de la topologie Lync Server 2013 et copie vers le support externe de l’installation Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) pour publier la topologie et la mettre à disposition de votre serveur Edge.

> [!NOTE]  
> Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge.

Pour réussir à publier, activer ou désactiver une topologie lorsque vous ajoutez ou supprimez un rôle serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Administrateurs du domaine. Il est également possible de déléguer les droits et autorisations d’administrateur appropriés pour ajouter des rôles serveur à un compte d’utilisateur. Pour plus d’informations, reportez-vous à [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) dans la documentation de déploiement consacrée aux serveurs Standard Edition ou Enterprise Edition. Pour toutes les autres modifications de configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est requise.

Si vous avez défini votre topologie Edge au moment de définir et de publier votre topologie interne et qu’aucune modification n’est requise dans la topologie Edge précédemment définie, il n’est pas nécessaire de la redéfinir ni de la republier. Appliquez la procédure suivante uniquement si vous avez besoin d’apporter des modifications à votre topologie Edge. Vous devez par contre mettre la topologie définie et publiée précédemment à la disposition de vos serveurs Edge. Pour cela, utilisez la procédure présentée dans la section [Exportation de la topologie Lync Server 2013 et copie vers le support externe de l’installation Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

> [!IMPORTANT]  
> Vous ne pouvez pas exécuter le Générateur de topologie à partir d’un serveur Edge. Vous devez l’exécuter à partir de votre serveur frontal ou de vos serveurs Standard Edition.

Le processus de définition de votre topologie de serveurs Edge s’effectue dans le Générateur de topologie. Les trois principaux types de topologies de serveurs Edge que vous pouvez planifier et configurer sont répertoriés ci-dessous :

  - Pour définir la topologie pour un serveur Edge unique

  - Pour définir la topologie pour un pool de serveurs Edge à charge équilibrée

  - Pour définir la topologie pour un pool de serveurs Edge à charge matérielle équilibrée

## Pour définir la topologie pour un serveur Edge unique

1.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

2.  Dans l’arborescence de la console, développez le site dans lequel vous souhaitez déployer un serveur Edge.

3.  Cliquez avec le bouton droit sur **Pools Edge** , puis cliquez sur **Nouveau pool de serveurs Edge** .

4.  Dans **Définir le nouveau pool Edge** , cliquez sur **Suivant** .

5.  Dans **Définir le nom de domaine complet du pool Edge** , procédez comme suit :
    
      - Dans **Nom de domaine complet du pool** , tapez le nom de domaine complet (FQDN) de l’interface interne pour le serveur Edge.
        
        > [!IMPORTANT]  
        > Le nom que vous spécifiez doit être identique au nom de l’ordinateur configuré sur le serveur. Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, pas un nom de domaine complet (FQDN). Le Générateur de topologie utilise des noms de domaine complets plutôt que des noms courts. Vous devez donc configurer un suffixe DNS sur le nom de l’ordinateur à déployer en tant que serveur Edge non joint à un domaine. Utilisez uniquement des caractères standard (A à Z, a à z, 0 à 9 et tirets) lorsque vous affectez des noms de domaine complets à vos serveurs Lync, serveurs Edge et pools. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard dans les noms de domaine complets ne sont souvent pas pris en charge par les DNS externes et les autorités publiques de certification (lorsque le nom de domaine complet doit être affecté à l’élément SN (nom de sujet) du certificat). Pour obtenir des informations sur l’ajout d’un suffixe DNS à un nom d’ordinateur, reportez-vous à <a href="lync-server-2013-configure-dns-for-edge-support.md">Configuration de DNS pour la prise en charge de périphérie dans Lync Server 2013</a>.    
      - Cliquez sur **Pool d’un seul ordinateur** , puis sur **Suivant** .

6.  Dans **Sélectionner les fonctionnalités** , procédez comme suit :
    
      - Si vous envisagez d’utiliser un seul nom de domaine complet et une seule adresse IP pour les services d’accès SIP, de conférence web Lync Server 2013 et Edge A/V, activez la case à cocher **Utiliser un seul nom de domaine complet (FQDN) et une seule adresse IP** .
    
      - Si vous envisagez d’activer la fédération, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)** .
        
        > [!NOTE]  
        > Vous pouvez activer cette option, mais un seul serveur Edge ou pool de serveurs Edge dans votre organisation peut être publié en externe pour la fédération. Tout accès par des utilisateurs fédérés, notamment les utilisateurs de messagerie instantanée publique, passe par le même serveur Edge unique ou pool de serveurs Edge. Par exemple, si votre déploiement inclut un pool de serveurs Edge ou un serveur Edge unique déployé à New York et un déployé à Londres et que vous activez la prise en charge de la fédération sur le pool de serveurs Edge ou le serveur Edge unique de New York, le trafic de signalisation des utilisateurs fédérés passera par le pool de serveurs Edge ou le serveur Edge unique de New York. Cela s’applique aussi aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le serveur Edge ou le pool de serveurs de Londres pour le trafic A/V.    
      - Si vous envisagez de prendre en charge le protocole XMPP (Extensible Messaging and Presence Protocol) pour votre déploiement, activez la case à cocher **Activer la fédération XMPP (port 5269)**

7.  Dans **Sélectionner les options IP** , procédez comme suit :
    
      - **Activer IPv4 sur l’interface interne**  : activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool de serveurs Edge.
    
      - **Activer IPv6 sur l’interface interne**  : activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool de serveurs Edge.
    
      - **Activer IPv4 sur l’interface externe**  : activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool de serveurs Edge.
    
      - **Activer IPv6 sur l’interface externe**  : activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool de serveurs Edge.
    
    Vous pouvez configurer le serveur Edge ou le pool de serveurs Edge pour utiliser une adresse NAT (Network Adresse Translation) pour les adresses IP externes. Pour ce faire, activez la case à cocher **L’adresse IP externe de ce pool Edge est convertie par NAT** .

8.  Dans **Noms de domaine complets externes** , procédez comme suit :
    
      - Si, dans **Sélectionner les fonctionnalités** , vous avez choisi d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez le nom de domaine complet externe dans **Accès SIP** .
        
        > [!NOTE]  
        > Si vous sélectionnez cette option, vous devez spécifier un numéro de port différent pour chacun des services Edge (paramètres de port recommandés : 5061 pour le service Edge d’accès, 444 pour le service Edge de conférence web et 443 pour le service Edge A/V). L’activation de cette option permet d’éviter les problèmes de connectivité potentiels et de simplifier la configuration, car vous pouvez alors utiliser le même numéro de port (par exemple, 443) pour les trois services.    
      - Si dans **Sélectionner les fonctionnalités** vous n’avez pas choisi d’utiliser un seul nom de domaine complet et une seule adresse IP, tapez les noms de domaine complets pour les services **Accès SIP** , **Conférence web** et **Audio Vidéo** , en conservant les ports par défaut.

9.  Cliquez sur **Suivant** .

10. Dans **Définir l’adresse IP interne** , tapez l’adresse IP de votre serveur Edge dans **Adresse IPv4 interne** et **Adresse IPv6 interne** selon votre configuration. Cliquez sur **Suivant** .

11. Dans **Définir l’adresse IP externe** , procédez comme suit :
    
      - Si vous avez décidé d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez l’adresse IPv4 externe du serveur Edge dans **Accès SIP** , puis cliquez sur **Suivant** .
    
      - Si vous avez choisi d’utiliser des adresses IPv6, tapez l’adresse IPv6 externe du serveur Edge dans **Accès SIP** , puis cliquez sur **Suivant** .
    
      - Si vous n’avez pas choisi d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez les adresses IPv4 externes du serveur Edge dans **Accès SIP** , **Conférence web** et **Conférence A/V** , puis cliquez sur **Suivant** .
    
      - Si vous avez choisi d’utiliser des adresses IPv6 et de ne pas utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez les adresses IPv6 externes du serveur Edge dans **Accès SIP** , **Conférence web** et **Conférence A/V** , puis cliquez sur **Suivant** .
        
        > [!NOTE]  
        > Si vous n’avez pas activé l’utilisation d’adresses IPv6, cette boîte de dialogue ne s’affiche pas.

12. Si vous avez choisi d’utiliser la conversion d’adresses réseau (NAT), une boîte de dialogue s’affiche. Dans **Adresse IPv4 publique pour le service Edge A/V** , tapez l’adresse IPv4 publique à convertir par NAT, puis cliquez sur **Suivant** .
    
    > [!NOTE]  
    > Il doit s’agir de l’adresse IP externe du service Edge A/V.

13. Si vous avez choisi d’utiliser la conversion d’adresses réseau (NAT) et des adresses IPv6, une boîte de dialogue s’affiche. Dans **Adresse IPv6 publique pour le service Edge A/V** , tapez l’adresse IPv6 publique à convertir par NAT, puis cliquez sur **Suivant** .
    
    > [!NOTE]  
    > Il doit s’agir de l’adresse IP externe du service Edge A/V.

14. Dans **Définir le tronçon suivant** , dans la zone **Pool du tronçon suivant** , sélectionnez le nom du pool interne qui peut être soit un pool frontal, soit un pool de serveurs Standard Edition. Ou, si votre déploiement inclut un directeur, sélectionnez-le, puis cliquez sur **Suivant** .

15. Dans **Pools frontaux associés** , spécifiez un ou plusieurs pools internes à associer à ce serveur Edge, notamment des pools frontaux et des serveurs Standard Edition Server, en sélectionnant les noms des pools internes qui utiliseront ce serveur Edge pour communiquer avec les utilisateurs externes pris en charge.
    
    > [!NOTE]  
    > Un seul pool de serveurs Edge à charge équilibrée ou un seul serveur Edge peut être associé à chaque pool interne pour le trafic A/V. Si vous disposez déjà d’un pool interne associé à un pool de serveurs Edge ou à un serveur Edge, un avertissement s’affiche vous indiquant que le pool interne est déjà associé à un pool de serveurs Edge ou à un serveur Edge. Si vous sélectionnez un pool déjà associé à un autre serveur Edge, cela modifiera l’association.

16. Cliquez sur **Terminer** .

17. Publiez votre topologie.

## Pour définir la topologie pour un pool de serveurs Edge avec charge DNS équilibrée

1.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

2.  Dans l’arborescence de la console, développez le site dans lequel vous souhaitez déployer les serveurs Edge.

3.  Cliquez avec le bouton droit sur **Pools de serveurs Edge** , puis cliquez sur **Nouveau pool de serveurs Edge** .

4.  Dans **Définir le nouveau pool Edge** , cliquez sur **Suivant** .

5.  Dans **Définir le nom de domaine complet du pool Edge** , procédez comme suit :
    
      - Dans **Nom de domaine complet du pool** , tapez le nom de domaine complet (FQDN) pour la connexion interne du pool de serveurs Edge.
        
        > [!IMPORTANT]  
        > Le nom de pool que vous indiquez doit être identique au nom du pool Edge interne. Il doit être défini comme nom de domaine complet (FQDN). Le Générateur de topologie utilise des noms de domaine complets plutôt que des noms courts. Utilisez uniquement des caractères standard (A à Z, a à z, 0 à 9 et tirets) lorsque vous attribuez des noms de domaine complets à vos serveurs Lync, serveurs Edge et pools. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard dans les noms de domaine complets ne sont souvent pas pris en charge par les DNS externes et les autorités publiques de certification (lorsque le nom de domaine complet doit être affecté à l’élément SN (nom du sujet) du certificat).    
      - Cliquez sur **Pool de plusieurs ordinateurs** , puis sur **Suivant** .

6.  Dans **Sélectionner les fonctionnalités** , procédez comme suit :
    
      - Si vous envisagez d’utiliser un seul nom de domaine complet et une seule adresse IP pour les services d’accès SIP, de conférence web Lync Server 2013 et Edge A/V, activez la case à cocher **Utiliser un seul nom de domaine complet et une seule adresse IP** .
    
      - Si vous envisagez d’activer la fédération, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)** . Cliquez sur **Suivant**
        
        > [!NOTE]  
        > Vous pouvez activer cette option, mais un seul pool de serveurs Edge ou serveur Edge dans votre organisation peut être publié en externe pour la fédération. Tout accès par des utilisateurs fédérés, notamment les utilisateurs de messagerie instantanée publique, passe par le même pool de serveurs Edge ou serveur Edge unique. Par exemple, si votre déploiement inclut un pool de serveurs Edge ou un serveur Edge unique déployé à New York et un déployé à Londres et que vous activez la prise en charge de la fédération sur le pool de serveurs Edge ou le serveur Edge unique de New York, le trafic de signalisation des utilisateurs fédérés passera par le pool de serveurs Edge ou le serveur Edge unique de New York. Cela s’applique aussi aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le pool de serveurs ou le serveur Edge de Londres pour le trafic A/V.    
      - Si vous envisagez de prendre en charge le protocole XMPP (Extensible Messaging and Presence Protocol) pour votre déploiement, activez la case à cocher **Activer la fédération XMPP (port 5269)**

7.  Cliquez sur **Suivant** .

8.  Dans **Sélectionner les options IP** , procédez comme suit :
    
      - **Activer IPv4 sur l’interface interne**  : activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool de serveurs Edge.
    
      - **Activer IPv6 sur l’interface interne**  : activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool de serveurs Edge.
    
      - **Activer IPv4 sur l’interface externe**  : activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool de serveurs Edge.
    
      - **Activer IPv6 sur l’interface externe**  : activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool de serveurs Edge.
    
    Vous pouvez configurer le serveur Edge ou le pool de serveurs Edge pour utiliser une adresse NAT (Network Adresse Translation) pour les adresses IP externes. Pour ce faire, activez la case à cocher **L’adresse IP externe de ce pool Edge est convertie par NAT** .

9.  Dans **Noms de domaine complets externes** , procédez comme suit :
    
      - Si, dans **Sélectionner les fonctionnalités** , vous avez choisi d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez le nom de domaine complet externe dans **Accès SIP** .
        
        > [!NOTE]  
        > Si vous sélectionnez cette option, vous devez spécifier un numéro de port différent pour chacun des services Edge (paramètres de port recommandés : 5061 pour le service Edge d’accès, 444 pour le service Edge de conférence web et 443 pour le service Edge A/V). L’activation de cette option permet d’éviter les problèmes de connectivité potentiels et de simplifier la configuration, car vous pouvez alors utiliser le même numéro de port (par exemple, 443) pour les trois services.    
      - Si, dans **Sélectionner les fonctionnalités** , vous n’avez pas décidé d’utiliser un seul nom de domaine complet et une seule adresse IP, tapez le nom de domaine complet que vous avez choisi pour le côté accessible au public du pool de serveurs Edge dans **Accès SIP** . Dans **Conférence web** , tapez le nom de domaine complet que vous avez choisi pour le côté accessible au public du pool de serveurs Edge. Dans **Audio/Vidéo** , tapez le nom de domaine complet que vous avez choisi pour le côté accessible au public du pool de serveurs Edge. Utilisez les ports par défaut.

10. Cliquez sur **Suivant** .

11. Dans **Définissez les ordinateurs inclus dans ce pool** , cliquez sur **Ajouter** .

12. Dans **FQDN et adresse IP internes** , procédez comme suit :
    
      - Dans **Adresse IPv4 interne** , tapez l’adresse IPv4 et l’**Adresse IPv6 interne** selon les besoins du premier serveur Edge à créer dans ce pool.
    
      - Dans **Nom de domaine complet (FQDN) interne** , tapez le nom de domaine complet du premier serveur Edge que vous souhaitez créer dans ce pool.
        
        > [!NOTE]  
        > Le nom que vous spécifiez doit être identique au nom de l’ordinateur configuré sur le serveur. Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, pas un nom de domaine complet (FQDN). Le Générateur de topologie utilise des noms de domaine complets plutôt que des noms courts. Vous devez donc configurer un suffixe DNS sur le nom de l’ordinateur à déployer en tant que serveur Edge non joint à un domaine. Utilisez uniquement des caractères standard (A à Z, a à z, 0 à 9 et tirets) lorsque vous affectez des noms de domaine complets à vos serveurs Lync, serveurs Edge, pools et tableaux. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard dans les noms de domaine complets ne sont souvent pas pris en charge par les DNS externes et les autorités publiques de certification (lorsque le nom de domaine complet doit être affecté à l’élément SN (nom du sujet) du certificat). Pour obtenir des informations sur l’ajout d’un suffixe DNS à un nom d’ordinateur, reportez-vous à <a href="lync-server-2013-configure-dns-for-edge-support.md">Configuration de DNS pour la prise en charge de périphérie dans Lync Server 2013</a>.

13. Cliquez sur **Suivant** .

14. Dans **Définir les adresses IP externes** , procédez comme suit :
    
      - Si vous avez décidé d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez l’adresse IP externe du serveur Edge dans **Accès SIP** .
    
      - Si vous avez décidé de ne pas utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service de conférence A/V, tapez l’adresse IP que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge dans **Accès SIP** . Dans **Conférence web** , tapez l’adresse IP que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge. Dans **Conférence A/V** , tapez l’adresse IP que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge.

15. Cliquez sur **Suivant** .

16. Si vous avez activé l’utilisation des adresses IPv6, dans **Définir l’adresse IP externe** , procédez comme suit :
    
      - Si vous avez décidé d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez l’adresse IPv6 externe du serveur Edge dans **Accès SIP** .
    
      - Si vous avez décidé de ne pas utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service de conférence A/V, tapez l’adresse IPv6 que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge dans **Accès SIP** . Dans **Conférence web** , tapez l’adresse IPv6 que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge. Dans **Conférence A/V** , tapez l’adresse IPv6 que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge.
    
    > [!NOTE]  
    > Si vous n’avez pas activé l’utilisation d’adresses IPv6, cette boîte de dialogue ne s’affiche pas.

17. Cliquez sur **Terminer** .
    
    > [!NOTE]  
    > Le premier serveur Edge créé dans votre pool s’affiche maintenant dans la boîte de dialogue <strong>Définissez les ordinateurs inclus dans ce pool</strong> .

18. Dans **Définissez les ordinateurs inclus dans ce pool** , cliquez sur **Ajouter** , puis répétez les étapes 11 à 14 pour le deuxième serveur Edge à ajouter à votre pool de serveurs Edge.

19. Après avoir exécuté les étapes 11 à 14, cliquez sur **Suivant** dans **Définissez les ordinateurs inclus dans ce pool** .
    
    > [!NOTE]  
    > À ce stade, les deux serveurs Edge sont visibles dans le pool.

20. Si vous avez choisi d’utiliser la conversion d’adresses réseau (NAT), une boîte de dialogue s’affiche. Dans **Adresse IP publique** , tapez les adresses IPv4 et IPv6 (le cas échéant) publiques à convertir par NAT, puis cliquez sur **Suivant** .
    
    > [!NOTE]  
    > Il doit s’agir de l’adresse IP externe du service Edge A/V.

21. Dans **Définir le tronçon suivant** , dans la liste **Pool du tronçon suivant** , sélectionnez le nom du pool interne qui peut être soit un pool de serveurs frontaux, soit un pool de serveurs Standard Edition. Ou, si votre déploiement inclut un directeur, sélectionnez son nom. Cliquez ensuite sur **Suivant** .

22. Dans **Pools frontaux associés** , spécifiez un ou plusieurs pools internes à associer à ce serveur Edge, notamment des pools frontaux et des serveurs Standard Edition, en sélectionnant les noms des pools internes qui utiliseront ce serveur Edge pour communiquer avec les utilisateurs externes pris en charge.
    
    > [!NOTE]  
    > Un seul pool de serveurs Edge à charge équilibrée ou un seul serveur Edge peut être associé à chaque pool interne pour le trafic A/V. Si vous disposez déjà d’un pool interne associé à un pool de serveurs Edge ou à un serveur Edge, un avertissement s’affiche vous indiquant que le pool interne est déjà associé à un pool de serveurs Edge ou à un serveur Edge. Si vous sélectionnez un pool déjà associé à un autre serveur Edge, cela modifiera l’association.

23. Cliquez sur **Terminer** .

24. Publiez votre topologie.

## Pour définir la topologie pour un pool de serveurs Edge à charge matérielle équilibrée

1.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

2.  Dans l’arborescence de la console, développez le site dans lequel vous souhaitez déployer les serveurs Edge.

3.  Cliquez avec le bouton droit sur **Pools de serveurs Edge** , puis cliquez sur **Nouveau pool de serveurs Edge** .

4.  Dans **Définir le nouveau pool Edge** , cliquez sur **Suivant** .

5.  Dans **Définir le nom de domaine complet du pool Edge** , procédez comme suit :
    
      - Dans **Nom de domaine complet** , tapez le nom de domaine complet (FQDN) de l’interface interne pour le pool de serveurs Edge.
        
        > [!IMPORTANT]  
        > Le nom de pool que vous indiquez doit être identique au nom du pool Edge interne. Il doit être défini comme nom de domaine complet (FQDN). Le Générateur de topologie utilise des noms de domaine complets plutôt que des noms courts. Utilisez uniquement des caractères standard (A à Z, a à z, 0 à 9 et tirets) lorsque vous attribuez des noms de domaine complets à vos serveurs Lync, serveurs Edge et pools. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard dans les noms de domaine complets ne sont souvent pas pris en charge par les DNS externes et les autorités publiques de certification (lorsque le nom de domaine complet doit être affecté à l’élément SN (nom du sujet) du certificat).    
    <!-- end list -->
    
      - Cliquez sur **Pool de plusieurs ordinateurs** , puis sur **Suivant** .

6.  Dans **Sélectionner les fonctionnalités** , procédez comme suit :
    
      - Si vous envisagez d’utiliser un seul nom de domaine complet et une seule adresse IP pour les services d’accès SIP, de conférence web Lync Server et Edge A/V, activez la case à cocher **Utiliser un seul nom de domaine complet et une seule adresse IP** .
    
      - Si vous envisagez d’activer la fédération, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)** .
        
        > [!NOTE]  
        > Vous pouvez activer cette option, mais un seul pool Edge ou serveur Edge dans votre organisation peut être publié en externe pour la fédération. Tout accès par des utilisateurs fédérés, notamment les utilisateurs de messagerie instantanée publique, passe par le même pool de serveurs Edge ou serveur Edge unique. Par exemple, si votre déploiement comprend un pool de serveurs Edge ou un serveur Edge unique déployé à New York, et un autre déployé à Londres, et que vous activez la prise en charge de fédération sur le pool de serveurs Edge ou serveur Edge unique de New York, le trafic de signalisation pour les utilisateurs fédérés passera par le pool de serveurs Edge ou serveur Edge unique de New York. Cela s’applique aussi aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le pool de serveurs ou le serveur Edge de Londres pour le trafic A/V.    
      - Si vous envisagez de prendre en charge le protocole XMPP (Extensible Messaging and Presence Protocol) pour votre déploiement, activez la case à cocher **Activer la fédération XMPP (port 5269)**

7.  Cliquez sur **Suivant** .

8.  Dans **Sélectionner les options IP** , procédez comme suit :
    
      - **Activer IPv4 sur l’interface interne**  : activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool de serveurs Edge.
    
      - **Activer IPv6 sur l’interface interne**  : activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool de serveurs Edge.
    
      - **Activer IPv4 sur l’interface externe**  : activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool de serveurs Edge.
    
      - **Activer IPv6 sur l’interface externe**  : activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool de serveurs Edge.
    
    > [!IMPORTANT]  
    > <strong>N’activez pas</strong> la case à cocher <strong>L’adresse IP externe de ce pool de serveurs Edge est convertie par NAT</strong> . La conversion d’adresses réseau (NAT) n’est pas prise en charge lorsque vous utilisez l’équilibrage de la charge matérielle.

9.  Dans **Noms de domaine complets externes** , procédez comme suit :
    
      - Si, dans **Sélectionner les fonctionnalités** , vous avez choisi d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez le nom de domaine complet externe dans **Accès SIP** .
        
        > [!NOTE]  
        > Si vous décidez d’activer cette option, vous devez spécifier un numéro de port différent pour chacun des services Edge (paramètres de port recommandés : 5061 pour le service Edge d’accès, 444 pour le service Edge de conférence web et 443 pour le service Edge A/V). L’activation de cette option permet d’éviter les problèmes de connectivité potentiels et de simplifier la configuration, car vous pouvez alors utiliser le même numéro de port (par exemple, 443) pour les trois services.    
      - Si, dans **Sélectionner les fonctionnalités** , vous n’avez pas décidé d’utiliser un seul nom de domaine complet et une seule adresse IP, tapez le nom de domaine complet que vous avez choisi pour le côté accessible au public du pool de serveurs Edge dans **Accès SIP** . Dans **Conférence web** , tapez le nom de domaine complet que vous avez choisi pour le côté accessible au public du pool de serveurs Edge. Dans **Audio/Vidéo** , tapez le nom de domaine complet que vous avez choisi pour le côté accessible au public du pool de serveurs Edge. Utilisez les ports par défaut.
        
        > [!NOTE]  
        > Ils serviront de noms de domaine complets des adresses IP virtuelles (VIP) accessibles au public.

10. Cliquez sur **Suivant** .

11. Dans **Définissez les ordinateurs inclus dans ce pool** , cliquez sur **Ajouter** .

12. Dans **Définir les adresses IP externes** , procédez comme suit :
    
      - Si vous avez décidé d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez l’adresse IPv4 externe du serveur Edge dans **Accès** **SIP** .
    
      - Si vous avez décidé de ne pas utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service de conférence A/V, tapez l’adresse IP que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge dans **Accès SIP** . Dans **Conférence web** , tapez l’adresse IP que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge. Dans **Conférence A/V** , tapez l’adresse IP que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge.

13. Cliquez sur **Suivant** .

14. Si vous avez activé l’utilisation des adresses IPv6, dans **Définir l’adresse IP externe** , procédez comme suit :
    
      - Si vous avez décidé d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez l’adresse IPv6 externe du serveur Edge dans **Accès SIP** .
    
      - Si vous avez décidé de ne pas utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service de conférence A/V, tapez l’adresse IPv6 que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge dans **Accès SIP** . Dans **Conférence web** , tapez l’adresse IPv6 que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge. Dans **Conférence A/V** , tapez l’adresse IPv6 que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge.
    
    > [!NOTE]  
    > Si vous n’avez pas activé l’utilisation d’adresses IPv6, cette boîte de dialogue ne s’affiche pas.

15. Cliquez sur **Terminer** .
    
    > [!NOTE]  
    > Le premier serveur Edge créé dans votre pool s’affiche maintenant dans la boîte de dialogue <strong>Définissez les ordinateurs inclus dans ce pool</strong> .

16. Dans **Définissez les ordinateurs inclus dans ce pool** , cliquez sur **Ajouter** , puis répétez les étapes 11 à 14 pour le deuxième serveur Edge que vous souhaitez ajouter à votre pool de serveurs Edge.

17. Après avoir exécuté les étapes 11 à 14, cliquez sur **Suivant** dans **Définissez les ordinateurs inclus dans ce pool** .
    
    > [!NOTE]  
    > À ce stade, les deux serveurs Edge sont visibles dans le pool.

18. Dans **Définir le tronçon suivant** , dans la liste **Pool du tronçon suivant** , sélectionnez le nom du pool interne qui peut être soit un pool de serveurs frontaux, soit un pool de serveurs Standard Edition. Ou, si votre déploiement inclut un directeur, sélectionnez son nom. Cliquez ensuite sur **Suivant** .

19. Dans **Pools frontaux associés** , spécifiez un ou plusieurs pools internes à associer à ce serveur Edge, notamment des pools frontaux et des serveurs Standard Edition, en sélectionnant les noms des pools internes qui utiliseront ce serveur Edge pour communiquer avec les utilisateurs externes pris en charge.
    
    > [!NOTE]  
    > Un seul pool de serveurs Edge à charge équilibrée ou un seul serveur Edge peut être associé à chaque pool interne pour le trafic A/V. Si vous disposez déjà d’un pool interne associé à un pool de serveurs Edge ou à un serveur Edge, un avertissement s’affiche vous indiquant que le pool interne est déjà associé à un pool de serveurs Edge ou à un serveur Edge. Si vous sélectionnez un pool déjà associé à un autre serveur Edge, cela modifiera l’association.

20. Cliquez sur **Terminer** .

21. Publiez votre topologie.

