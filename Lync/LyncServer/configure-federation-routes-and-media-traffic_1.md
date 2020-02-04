---
title: Configuration des itinéraires de fédération et du trafic multimédia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af8228a7537f1bbef4e92af852834459281a817
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728174"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configuration des itinéraires de fédération et du trafic multimédia

 


La Fédération est une relation d’approbation entre au moins deux domaines SIP, qui permet aux utilisateurs d’organisations distinctes de communiquer au sein des frontières du réseau. Après avoir effectué une migration vers votre pool de pilotes de Lync Server 2013, vous devez effectuer une transition de l’itinéraire de Fédération de vos serveurs Microsoft Office Communications Server 2007 R2 vers l’itinéraire de Fédération de vos serveurs Edge Lync Server 2013.

Utilisez les procédures qui suivent pour basculer l’itinéraire de la Fédération et l’itinéraire de trafic multimédia de votre serveur et directeur Office Communications Server 2007 R2 vers votre serveur Edge Lync Server 2013 pour un déploiement sur site.


> [!IMPORTANT]  
> La modification de l’itinéraire et de l’itinéraire de trafic multimédia requis pour la planification de la maintenance des serveurs Lync Server 2013 et Office Communications Server 2007 R2. Ce processus de transition complet signifie également que l’accès fédéré ne sera pas disponible pendant la durée de la période d’interruption. Nous vous conseillons de planifier le temps d’arrêt à un moment où vous vous attendez à un minimum d’activités utilisateur. Vous devez également fournir une notification suffisante à vos utilisateurs finaux. Planifiez en conséquence pour cette interruption et définissez les attentes appropriées au sein de votre organisation.




> [!IMPORTANT]  
> Si votre serveur Edge Office Communications Server 2007 R2 est configuré de manière à utiliser le même nom de domaine complet pour le service Edge d’accès, le service Edge de conférence Web et le service Edge A/V, les procédures de cette section pour faire basculer le paramètre de Fédération vers un serveur Edge Lync Server 2013 ne sont pas prises en charge. Si les services d’arête hérités sont configurés pour utiliser le même nom de domaine complet (FQDN), vous devez tout d’abord migrer tous vos utilisateurs d’Office Communications Server 2007 R2 vers Lync Server 2013, puis désaffecter le serveur Edge Office Communications Server 2007 R2 avant d’activer la Fédération. Serveur Edge Lync Server 2013. Pour obtenir des détails, consultez les rubriques suivantes : 
> <UL>
> <LI>
> <P><A href="move-remaining-users-to-lync-server-2013_1.md">Déplacement des autres utilisateurs vers Lync Server 2013</A></P>
> <LI>
> <P>"Supprimer les serveurs et les rôles serveur" sur<A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></P></LI></UL>




> [!IMPORTANT]  
> Si votre Fédération XMPP est routée via un serveur Edge Lync Server 2013, les utilisateurs d’Office Communications Server 2007 R2 hérités ne seront pas en mesure de communiquer avec le partenaire fédéré de XMPP tant que tous les utilisateurs n’ont pas été déplacés vers Lync Server 2013, les stratégies XMPP et des certificats ont été configurés, le partenaire fédéré de XMPP a été configuré sur Lync Server 2013, et la mise à jour des entrées DNS.



Pour publier, activer ou désactiver une topologie lors de l’ajout ou de la suppression d’un rôle serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Admins du domaine. Il est également possible de déléguer les droits d’utilisateur et les autorisations nécessaires pour ajouter des rôles de serveur. Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync server 2013](lync-server-2013-delegate-setup-permissions.md) dans la documentation de déploiement Standard Edition Server ou Enterprise Edition Server. Pour les autres modifications de configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est requise.

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Pour supprimer l’Association de Fédération héritée des sites Lync Server 2013

1.  Ouvrez la topologie de pool pilote à l’aide du générateur de topologie.

2.  Dans le volet gauche, accédez au nœud site.

3.  Cliquez avec le bouton droit sur le site, puis cliquez sur **modifier les propriétés**.

4.  Dans le volet gauche, sélectionnez **routage de Fédération** .

5.  Sous affectation de l’itinéraire de Fédération de site, désactivez la case à cocher en regard de **activer la Fédération SIP** pour désactiver le routage de Fédération via le **BackCompatSite**.
    
    ![Boîte de dialogue Modifier les propriétés, itinéraire de Fédération](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, itinéraire de Fédération")

6.  Cliquez sur **OK** pour fermer la page modifier les propriétés.

7.  Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **serveur Lync**.

8.  Dans le menu **action** , cliquez sur **publier la topologie** et terminer l’Assistant.

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Pour configurer le serveur de périphérie traditionnel en tant que serveur Edge non fédéré

1.  Dans le **Générateur de topologie**, à partir du menu d' **action** , cliquez sur **fusionner Office Communications Server 2007 R2**.

2.  Cliquez sur **Suivant** pour continuer.

3.  Dans la **configuration spécifier le bord**, sélectionnez le **FQDN interne du serveur Edge** actuellement configuré pour la Fédération, puis cliquez sur **modifier**.
    
    ![Fusionner la topologie OCS 2007 R2, spécifier l’installation de Microsoft Edge](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Fusionner la topologie OCS 2007 R2, spécifier l’installation de Microsoft Edge")

4.  Cliquez sur **suivant** et acceptez les paramètres par défaut jusqu’à ce que vous atteigniez la page **spécifier le bord externe** :
    
    ![Le générateur de topologie spécifie une page de bord externe](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Le générateur de topologie spécifie une page de bord externe")

5.  Dans **spécifier le bord externe**, décochez la case **ce pool de bords est utilisé pour la connectivité de Fédération et de messagerie instantanée publique** . Cette opération a pour supprimer l’Association de Fédération avec le BackCompatSite.
    

    > [!IMPORTANT]  
    > Cette étape est importante. Vous devez désactiver cette option pour supprimer l’Association de Fédération héritée.



6.  Cliquez sur **suivant** et acceptez les paramètres par défaut des pages restantes de l’Assistant.

7.  En **Résumé**, cliquez sur **suivant** pour commencer à fusionner les topologies.

8.  Dans la colonne **État** , assurez-vous que la valeur est **succès**, puis cliquez sur **Terminer** pour fermer l’Assistant.

9.  Dans le menu **action** , cliquez sur **publier la topologie**, puis sur **suivant**.

10. Lorsque l' **Assistant Publication** est terminé, cliquez sur **Terminer** pour fermer l’Assistant.
    
    ![Générateur de topologie avec site affiché après la fusion](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Générateur de topologie avec site affiché après la fusion")
    
    Comme indiqué dans l’illustration précédente, la **Fédération SIP** située sous **affectation** de l’itinéraire de Fédération de site est définie sur **désactivé**.

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a>Pour configurer des certificats sur le serveur Edge Lync Server 2013

1.  Exportez le certificat de proxy d’accès externe, avec la clé privée, à partir du serveur Edge Office Communications Server 2007 R2 hérité.

2.  Sur le serveur Edge Lync Server 2013, importez le certificat externe de proxy d’accès à partir de l’étape précédente.

3.  Attribuez le certificat externe du proxy d’accès à l’interface externe de Lync Server 2013 du serveur Edge.

4.  Le certificat d’interface interne du serveur Edge Lync Server 2013 ne doit pas être modifié.

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a>Pour modifier l’itinéraire de Fédération d’Office Communications Server 2007 R2 pour utiliser Lync Server 2013 Edge Server

1.  Sur le serveur Office Communications Server 2007 R2 Standard Edition Server ou front end Server, ouvrez l’outil d’administration Office Communications Server 2007 R2.

2.  Dans le volet gauche, développez le nœud supérieur, puis cliquez avec le bouton droit sur le nœud de la **forêt** . Sélectionnez **Propriétés**, puis cliquez sur **propriétés globales**.

3.  Cliquez sur l’onglet **Fédération** .

4.  Activez la case à cocher pour activer la connectivité de Fédération et de messagerie instantanée publique.

5.  Entrez le nom de domaine complet (FQDN) du serveur Edge Lync Server 2013, puis cliquez sur **OK**.
    
    ![Propriétés internationales d’OCS, onglet Fédération](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Propriétés internationales d’OCS, onglet Fédération")

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Pour activer la Fédération de serveur Edge Lync Server 2013

1.  Dans le générateur de topologie, dans le volet gauche, accédez au nœud de **pools de périphériques** Lync Server 2013.

2.  Développez le nœud, cliquez avec le bouton droit sur le serveur Edge indiqué, puis cliquez sur **modifier les propriétés**.
    

    > [!NOTE]  
    > La Fédération ne peut être activée que pour un seul pool de bords. Si vous avez plusieurs pools de bords, sélectionnez-en un pour les utiliser comme pools de frontière de Fédération.



3.  Dans la page **général** , activez la case à cocher **activer la Fédération pour ce pool Edge (port 5061)** .
    
    ![Modification des propriétés, générale, activer la Fédération Edge](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Modification des propriétés, générale, activer la Fédération Edge")

4.  Cliquez sur **OK** pour fermer la page modifier les propriétés.

5.  Ensuite, accédez au nœud site.

6.  Cliquez avec le bouton droit sur le site, puis cliquez sur **modifier les propriétés**.

7.  Dans le volet de gauche, cliquez sur **route de Fédération**.

8.  Sous **affectation**de l’itinéraire de la Fédération de sites, sélectionnez **activer la Fédération SIP**, puis dans la liste, sélectionnez le serveur Edge Lync Server 2013.

9.  Cliquez sur **OK** pour fermer la page **modifier les propriétés** .
    
    ![Modification des propriétés, général et pool de périphérie](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Modification des propriétés, général et pool de périphérie")
    
    Pour les déploiements multisites, procédez comme suit sur chaque site.

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Pour configurer le chemin multimédia sortant du serveur Lync Server 2013 Edge

1.  Dans le **Générateur de topologie**, accédez au pool Lync Server 2013 inférieur aux **serveurs front end standard** ou aux **Pools front-end Enterprise Edition**.

2.  Cliquez avec le bouton droit sur la liste, puis cliquez sur **modifier les propriétés**.

3.  Dans la section **associations** , activez la case à cocher **associer le pool Edge (pour les composants multimédias)** .

4.  Dans la zone de liste déroulante, sélectionnez le serveur Edge Lync Server 2013.
    
    ![Boîte de dialogue Modifier les propriétés, groupe de bords](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, groupe de bords")

5.  Cliquez sur **OK** pour fermer la page **modifier les propriétés** .

## <a name="to-publish-edge-server-configuration-changes"></a>Pour publier les modifications de configuration de serveur Edge

1.  Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **serveur Lync**.

2.  Dans le menu **action** , sélectionnez **publier la topologie** et terminer l’Assistant.

3.  Attendez la fin de la réplication Active Directory pour tous les pools du déploiement.
    

    > [!NOTE]  
    > Le message suivant risque de s’afficher :<BR><STRONG>AVERTISSEMENT : la topologie comporte plus d’un serveur Edge fédéré. Cela peut se produire lors de la migration vers une version plus récente du produit. Dans ce cas, un seul serveur Edge serait utilisé activement pour la Fédération. Vérifiez que l’enregistrement SRV DNS externe pointe vers le serveur Edge approprié. Si vous voulez déployer plusieurs serveurs de frontière de Fédération de manière à être actifs en même temps (c’est-à-dire, pas dans un scénario de migration), vérifiez que tous les partenaires fédérés utilisent Office Communications Server 2007 R2 ou Lync Server. Vérifiez que l’enregistrement SRV DNS externe recense tous les serveurs Edge compatibles avec la Fédération.</STRONG><BR>Cet avertissement est attendu et peut être ignoré en toute sécurité.



## <a name="to-verify-federation-and-remote-access-for-external-users"></a>Pour vérifier la Fédération et l’accès à distance pour les utilisateurs externes

1.  À partir du serveur frontal Lync Server 2013, ouvrez Lync Server Management Shell.

2.  Pour vérifier l’état de la Fédération et de l’accès à distance, à partir de la ligne de commande, tapez ce qui suit :
    
        Get-CsAccessEdgeConfiguration

3.  Pour activer la Fédération et l’accès à distance, à partir de la ligne de commande, tapez ce qui suit :
    
        Set-CsAccessEdgeConfiguration
    
    Pour plus d’informations sur ces applets de commande, reportez-vous aux rubriques suivantes : [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) et [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).

4.  Attendez la fin de la réplication avant de mettre en ligne les serveurs Edge Lync Server 2013 et de tester la Fédération et l’accès externe.

## <a name="to-configure-lync-server-2013-edge-server"></a>Pour configurer Lync Server 2013 Edge Server

1.  Accédez à tous les serveurs Edge Lync Server 2013 en ligne.

2.  Mettez à jour les règles de routage de pare-feu externe ou les paramètres de l’équilibrage de charge matérielle pour envoyer le trafic SIP pour l’accès externe (en général, le port 443) et la Fédération (en général, le port 5061) vers le serveur Edge Lync Server 2013, au lieu du serveur Edge hérité.
    

    > [!NOTE]  
    > Si vous n’avez pas d’équilibrage de charge matérielle, vous devez mettre à jour l’enregistrement DNS A pour la Fédération pour résoudre le nouveau serveur Lync Server Access Edge. Pour effectuer cette opération avec un minimum de perturbation, réduisez la valeur de durée de vie du nom de domaine complet (FQDN) du périmètre du serveur Lync Server de façon à ce qu’elle pointe vers le nouveau serveur Lync Server Access Edge.



3.  Ensuite, arrêtez le **Edge d’accès de Lync Server** depuis chaque ordinateur du serveur Edge.

4.  À partir de chaque ordinateur serveur Edge hérité, ouvrez l’application **services** à partir des **Outils d’administration**.

5.  Dans la liste des services, recherchez **Edge Access pour Office Communications Server**.

6.  Cliquez avec le bouton droit sur le nom des services, puis sélectionnez **arrêter** pour arrêter le service.

7.  Définissez le type de démarrage sur **désactivé**.

8.  Cliquez sur **OK** pour fermer la fenêtre **Propriétés** .

## <a name="to-test-connectivity-of-external-users-and-external-access"></a>Pour tester la connectivité des utilisateurs externes et l’accès externe

  - Utilisateurs d’au moins un domaine fédéré, utilisateur interne sur Lync Server 2013 et un utilisateur sur Office Communications Server 2007 R2. Testez la messagerie instantanée, la présence, les appels audio/vidéo (A/V) et le partage de bureau.

  - Utilisateurs de chaque fournisseur de services de messagerie instantanée publique pris en charge par votre organisation (et pour lequel la mise en service a été effectuée) communique avec un utilisateur sur Lync Server 2013 et un utilisateur sur Office Communications Server 2007 R2.

  - Vérifiez que les utilisateurs anonymes peuvent participer à des conférences.

  - Un utilisateur hébergé sur Office Communications Server 2007 R2 à l’aide de l’accès des utilisateurs distants (connexion à Office Communications Server 2007 R2 hors de l’intranet, mais sans VPN) avec un utilisateur sur Lync Server 2013, et un utilisateur sur Office Communications Server 2007 R2. Testez la messagerie instantanée, la présence, A/V et le partage du bureau.

  - Un utilisateur hébergé sur Lync Server 2013 à l’aide de l’accès des utilisateurs distants (connexion à Lync Server 2013 hors de l’intranet, mais sans VPN) avec un utilisateur sur Lync Server 2013 et un utilisateur sur Office Communications Server 2007 R2. Testez la messagerie instantanée, la présence, A/V et le partage du bureau.

