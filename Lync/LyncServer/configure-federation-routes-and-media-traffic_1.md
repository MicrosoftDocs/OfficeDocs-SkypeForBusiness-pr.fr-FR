---
title: Configurer les itinéraires de fédération et le trafic multimédia
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d6af77188809b092050629c1b74cdab8b20a2cc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754960"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configurer les itinéraires de fédération et le trafic multimédia

 


La fédération est une relation d’approbation entre deux ou plusieurs domaines SIP qui permet aux utilisateurs d’organisations distinctes de communiquer au-delà des limites des réseaux. Une fois que vous avez effectué la migration vers votre pool pilote Lync Server 2013, vous devez passer de l’itinéraire de Fédération de vos serveurs Edge Microsoft Office Communications Server 2007 R2 à l’itinéraire de Fédération de vos serveurs Edge Lync Server 2013.

Utilisez les procédures suivantes pour effectuer la transition de l’itinéraire de Fédération et de l’itinéraire de trafic multimédia de votre serveur Edge et directeur Office Communications Server 2007 R2 vers votre serveur Edge Lync Server 2013, pour un déploiement sur un seul site.


> [!IMPORTANT]  
> La modification de l’itinéraire de Fédération et de l’itinéraire de trafic multimédia nécessite de planifier le temps d’arrêt de la maintenance pour les serveurs Edge Lync Server 2013 et Office Communications Server 2007 R2. Ce processus de transition signifie également que l’accès fédéré sera indisponible pendant la durée de l’interruption. Vous devez donc planifier cette interruption à un moment où l’activité des utilisateurs sera minimale. Prévoyez aussi d’en informer les utilisateurs finaux suffisamment à l’avance. Anticipez cette interruption à tous les niveaux et informez-en votre organisation afin qu’elle s’y prépare en conséquence.




> [!IMPORTANT]  
> Si votre serveur Edge Office Communications Server 2007 R2 hérité est configuré pour utiliser le même nom de domaine complet pour le service Edge d’accès, le service Edge de conférence Web et le service Edge A/V, les procédures de cette section pour faire passer le paramètre de Fédération à un serveur Edge Lync Server 2013 ne sont pas prises en charge. Si les services Edge hérités sont configurés pour utiliser le même nom de domaine complet, vous devez d’abord migrer tous vos utilisateurs d’Office Communications Server 2007 R2 vers Lync Server 2013, puis désactivez le serveur Edge Office Communications Server 2007 R2 avant d’activer la Fédération sur le serveur Edge Lync Server 2013. Pour plus de détails, consultez les rubriques suivantes : 
> <UL>
> <LI>
> <P><A href="move-remaining-users-to-lync-server-2013_1.md">Déplacer les utilisateurs restants vers Lync Server 2013</A></P>
> <LI>
> <P>« Supprimer les serveurs et les rôles serveur » à l’adresse<A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></P></LI></UL>




> [!IMPORTANT]  
> Si votre Fédération XMPP est acheminée via un serveur Edge Lync Server 2013, les utilisateurs hérités d’Office Communications Server 2007 R2 ne seront pas en mesure de communiquer avec le partenaire fédéré XMPP tant que tous les utilisateurs n’ont pas été déplacés vers Lync Server 2013, les stratégies XMPP et les certificats ont été configurés, le partenaire fédéré XMPP a été configuré sur Lync Server 2013



Pour publier, activer ou désactiver une topologie lors de l’ajout ou de la suppression d’un rôle de serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Administrateurs du domaine. Il est également possible de déléguer les autorisations et les droits d’utilisateur voulus pour ajouter des rôles de serveur. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) dans la documentation de déploiement du serveur Standard Edition Server ou Enterprise Edition. Pour les autres modifications de configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est requise.

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Pour supprimer l’Association de Fédération héritée des sites Lync Server 2013

1.  Ouvrez la topologie du pool pilote à l’aide du générateur de topologie.

2.  Dans le volet gauche, naviguez jusqu’au nœud du site.

3.  Cliquez avec le bouton droit sur le site, puis cliquez sur **Modifier les propriétés**.

4.  Sélectionnez **Itinéraire de fédération** dans le volet gauche.

5.  Sous attribution de l’itinéraire de Fédération du site, désactivez la case à cocher en regard de **activer la Fédération SIP** pour désactiver l’itinéraire de Fédération via le **BackCompatSite**.
    
    ![Boîte de dialogue Modifier les propriétés, itinéraire de Fédération](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, itinéraire de Fédération")

6.  Cliquez sur **OK** pour fermer la page Modifier les propriétés.

7.  Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **Lync Server**.

8.  Dans le menu **Actions**, cliquez sur **Publier la topologie** et terminez l’Assistant.

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Pour configurer le serveur Edge hérité en tant que serveur Edge non-fédérant

1.  Dans le **Générateur de topologie**, dans le menu **action** , cliquez sur **fusionner la topologie Office Communications Server 2007 R2**.

2.  Cliquez sur **Suivant **pour continuer.

3.  Dans **Spécifier la configuration Edge**, sélectionnez le **Nom de domaine complet interne du serveur Edge** qui est actuellement configuré pour la fédération, puis cliquez sur **Modifier**.
    
    ![Fusionner la topologie OCS 2007 R2, spécifier la configuration Edge](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Fusionner la topologie OCS 2007 R2, spécifier la configuration Edge")

4.  Cliquez sur **Suivant** et acceptez les paramètres par défaut jusqu’à ce que vous accédiez à la page **Spécifier la configuration Edge externe** :
    
    ![Page spécifier le générateur de topologies](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Page spécifier le générateur de topologies")

5.  In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box. This will remove the federation association with the BackCompatSite.
    

    > [!IMPORTANT]  
    > This step is important. You must clear this option to remove the legacy federation association.



6.  Cliquez sur **Suivant** et acceptez les paramètres par défaut des pages restantes de l’Assistant.

7.  Dans **Sommaire**, cliquez sur **Suivant** pour commencer à fusionner les topologies.

8.  Dans la colonne **État** , vérifiez que la valeur est **opération réussie**, puis cliquez sur **Terminer** pour fermer l’Assistant.

9.  Dans le menu **Action**, sélectionnez **Publier la topologie**, puis cliquez sur **Suivant**.

10. Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer.
    
    ![Générateur de topologies avec site affiché après la fusion](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Générateur de topologies avec site affiché après la fusion")
    
    Comme indiqué dans la figure précédente, la **Fédération SIP** située sous **attribution** de l’itinéraire de Fédération du site est définie sur **désactivé**.

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a>Pour configurer des certificats sur le serveur Edge Lync Server 2013

1.  Exportez le certificat de proxy d’accès externe, avec la clé privée, à partir du serveur Edge Office Communications Server 2007 R2 hérité.

2.  Sur le serveur Edge Lync Server 2013, importez le certificat externe de proxy d’accès à partir de l’étape précédente.

3.  Affectez le certificat externe de proxy d’accès à l’interface externe Lync Server 2013 du serveur Edge.

4.  Le certificat d’interface interne du serveur Edge Lync Server 2013 ne doit pas être modifié.

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a>Pour modifier l’itinéraire de Fédération Office Communications Server 2007 R2 afin d’utiliser le serveur Edge Lync Server 2013

1.  Sur le serveur Office Communications Server 2007 R2 Standard Edition ou le serveur frontal, ouvrez l’outil d’administration Office Communications Server 2007 R2.

2.  In the left pane, expand the top node, and then right-click the **Forest** node. Select **Properties**, and then click **Global Properties**.

3.  Cliquez sur l’onglet **Fédération**.

4.  Activez la case à cocher pour activer la fédération et la solution PIC (Public IM Connectivity).

5.  Entrez le nom de domaine complet (FQDN) du serveur Edge Lync Server 2013, puis cliquez sur **OK**.
    
    ![Propriétés globales OCS, onglet Fédération](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Propriétés globales OCS, onglet Fédération")

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Pour activer la fédération du serveur Edge Lync Server 2013

1.  Dans le volet de gauche du générateur de topologie, accédez au nœud des **Pools** de serveurs Lync Server 2013.

2.  Développez le nœud, cliquez avec le bouton droit sur le serveur Edge listé, puis cliquez sur **Modifier les propriétés**.
    

    > [!NOTE]  
    > La Fédération ne peut être activée que pour un seul pool de serveurs Edge. Si vous avez plusieurs pools de serveurs Edge, sélectionnez-en un à utiliser comme pool Edge fédérateur.



3.  Dans la page **Général**, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**.
    
    ![Modifier les propriétés, général, activer la Fédération Edge](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Modifier les propriétés, général, activer la Fédération Edge")

4.  Cliquez sur **OK** pour fermer la page Modifier les propriétés.

5.  Naviguez ensuite vers le nœud du site.

6.  Cliquez avec le bouton droit sur le site, puis cliquez sur **Modifier les propriétés**.

7.  Dans le volet gauche, cliquez sur **Itinéraire de fédération**.

8.  Sous **attribution**de l’itinéraire de Fédération du site, sélectionnez **activer la Fédération SIP**, puis dans la liste, sélectionnez le serveur Edge Lync Server 2013 répertorié.

9.  Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.
    
    ![Modifier les propriétés, général, associer un pool de serveurs Edge](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Modifier les propriétés, général, associer un pool de serveurs Edge")
    
    Pour les déploiements sur plusieurs sites, effectuez cette procédure sur chaque site.

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Pour configurer le chemin d’accès des médias sortants du serveur Edge Lync Server 2013

1.  Dans le **Générateur de topologies**, accédez au pool Lync Server 2013 sous **serveurs frontaux Standard Edition** ou **Pools frontaux Enterprise Edition**.

2.  Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.

3.  Dans la section **Associations**, activez la case à cocher **Associer un pool Edge (pour les composants multimédias)**.

4.  Dans la zone de liste déroulante, sélectionnez le serveur Edge Lync Server 2013.
    
    ![Boîte de dialogue Modifier les propriétés, associer un pool de serveurs Edge](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, associer un pool de serveurs Edge")

5.  Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.

## <a name="to-publish-edge-server-configuration-changes"></a>Pour publier les modifications de configuration du serveur Edge

1.  Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **Lync Server**.

2.  Dans le menu **Actions**, sélectionnez **Publier la topologie** et terminez l’Assistant.

3.  Attendez que la réplication Active Directory se produise sur tous les pools de serveurs impliqués dans le déploiement.
    

    > [!NOTE]  
    > Vous pouvez voir le message suivant :<BR><STRONG>Attention : La topologie contient plusieurs serveurs Edge fédérés. Cela peut se produire au cours d’une migration vers une version plus récente du produit. Dans ce cas, un seul serveur Edge serait utilisé activement pour la fédération. Vérifiez que l’enregistrement SRV DNS externe pointe vers le serveur Edge voulu. Si vous voulez déployer plusieurs serveurs Edge de fédération de sorte qu’ils soient actifs simultanément (pas un scénario de migration, donc), vérifiez que tous les partenaires fédérés utilisent Office Communications Server 2007 R2 ou Lync Server. Vérifiez que l’enregistrement SRV DNS externe liste tous les serveurs Edge activés pour la fédération.</STRONG><BR>Cet avertissement est attendu et peut être ignoré en toute sécurité.



## <a name="to-verify-federation-and-remote-access-for-external-users"></a>Pour vérifier la Fédération et l’accès à distance pour les utilisateurs externes

1.  À partir du serveur frontal Lync Server 2013, ouvrez Lync Server Management Shell.

2.  Pour vérifier l’état de la Fédération et de l’accès à distance, à partir de la ligne de commande, tapez ce qui suit :
    
        Get-CsAccessEdgeConfiguration

3.  Pour activer la Fédération et l’accès à distance, à partir de la ligne de commande, tapez ce qui suit :
    
        Set-CsAccessEdgeConfiguration
    
    Pour plus d’informations sur ces cmdlets, consultez les rubriques suivantes : [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) et [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).

4.  Attendez la fin de la réplication avant de mettre en ligne les serveurs Edge Lync Server 2013, et de tester la Fédération et l’accès externe.

## <a name="to-configure-lync-server-2013-edge-server"></a>Pour configurer le serveur Edge Lync Server 2013

1.  Mettez tous les serveurs Edge Lync Server 2013 en ligne.

2.  Mettez à jour les règles de routage du pare-feu externe ou les paramètres du programme d’équilibrage de la charge matérielle pour envoyer le trafic SIP pour l’accès externe (généralement le port 443) et la Fédération (généralement le port 5061) vers le serveur Edge Lync Server 2013, au lieu du serveur Edge hérité.
    

    > [!NOTE]  
    > Si vous ne disposez pas d’un programme d’équilibrage de la charge matérielle, vous devez mettre à jour l’enregistrement DNS A pour la Fédération afin de résoudre le nouveau serveur Edge Lync Server Access. Pour effectuer cette opération en cas de perturbation minimale, réduisez la valeur de durée de vie pour le nom de domaine complet du serveur Edge d’accès externe Lync Server de sorte que lorsque DNS est mis à jour pour pointer vers le nouveau serveur Edge Lync Server Access, la Fédération et l’accès à distance seront mis à jour rapidement.



3.  Ensuite, arrêtez le serveur **Edge d’accès Lync Server** à partir de chaque ordinateur serveur Edge.

4.  À partir de chaque ordinateur serveur Edge hérité, ouvrez l’applet **services** à partir des **Outils d’administration**.

5.  Dans la liste des services, recherchez **Serveur Edge d’accès Office Communications Server**.

6.  Cliquez avec le bouton droit sur le nom du service, puis sélectionnez **Arrêter** pour arrêter le service.

7.  Définissez le type de démarrage sur **Désactivé**.

8.  Cliquez sur **OK** pour fermer la fenêtre **Propriétés**.

## <a name="to-test-connectivity-of-external-users-and-external-access"></a>Pour tester la connectivité des utilisateurs externes et de l’accès externe

  - Utilisateurs d’au moins un domaine fédéré, un utilisateur interne sur Lync Server 2013 et un utilisateur sur Office Communications Server 2007 R2. Testez la messagerie instantanée, la présence, l’audio/vidéo (A/V) et le partage de Bureau.

  - Les utilisateurs de chaque fournisseur de services de messagerie instantanée public pris en charge par votre organisation (et pour lequel le provisionnement a été effectué) communiquant avec un utilisateur sur Lync Server 2013 et un utilisateur sur Office Communications Server 2007 R2.

  - Vérifiez que les utilisateurs anonymes peuvent participer à des conférences.

  - Un utilisateur hébergé sur Office Communications Server 2007 R2 à l’aide de l’accès des utilisateurs distants (connexion à Office Communications Server 2007 R2 depuis l’extérieur de l’intranet mais sans VPN) avec un utilisateur sur Lync Server 2013, et un utilisateur sur Office Communications Server 2007 R2. Testez la messagerie instantanée, la présence, l’audio/vidéo et le partage de Bureau.

  - Un utilisateur hébergé sur Lync Server 2013 à l’aide de l’accès des utilisateurs distants (connexion à Lync Server 2013 depuis l’extérieur de l’intranet mais sans VPN) avec un utilisateur sur Lync Server 2013, et un utilisateur sur Office Communications Server 2007 R2. Testez la messagerie instantanée, la présence, l’audio/vidéo et le partage de Bureau.

