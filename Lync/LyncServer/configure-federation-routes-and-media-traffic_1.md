---
title: Configuration des itinéraires de fédération et du trafic multimédia
TOCTitle: Configuration des itinéraires de fédération et du trafic multimédia
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49891598
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des itinéraires de fédération et du trafic multimédia

 

_**Dernière rubrique modifiée :** 2016-12-08_

La fédération est une relation d’approbation entre deux ou plusieurs domaines SIP qui permet aux utilisateurs d’entreprises distinctes de communiquer au-delà des limites du réseau. Après avoir effectué la migration vers votre premier pool Lync Server 2013, vous devez effectuer une transition de l’itinéraire de la fédération de vos serveurs Edge Microsoft Office Communications Server 2007 R2 vers l’itinéraire de fédération de vos serveurs Edge Lync Server 2013.

Utilisez les procédures suivantes pour effectuer la transition de l’itinéraire de fédération et de l’itinéraire de trafic multimédia de vos serveurs Edge et directeur Office Communications Server 2007 R2 vers votre serveur Edge Lync Server 2013, pour un déploiement de site unique.

> [!IMPORTANT]  
> La modification de l’itinéraire de fédération et de l’itinéraire de trafic multimédia nécessite que vous planifiiez une interruption de maintenance pour les serveurs Edge Lync Server 2013 et Office Communications Server 2007 R2. Ce processus de transition signifie également que l’accès fédéré sera indisponible pendant la durée de l’interruption. Vous devez donc planifier cette interruption à un moment où l’activité des utilisateurs sera minimale. Prévoyez aussi d’en informer les utilisateurs finaux suffisamment à l’avance. Anticipez cette interruption à tous les niveaux et informez-en votre entreprise afin qu’elle s’y prépare en conséquence.

> [!IMPORTANT]  
> Si votre serveur Edge Office Communications Server 2007 R2 hérité est configuré de manière à utiliser le même nom de domaine complet (FQDN) pour le service Edge d’accès, le service Edge de conférence web et le service Edge A/V, les procédures de transition, présentées dans cette section, d’un paramètre de fédération vers un serveur Edge Lync Server 2013 ne sont pas prises en charge. Si les services Edge hérités sont configurés pour utiliser le même FQDN, vous devez d’abord migrer tous vos utilisateurs entre Office Communications Server 2007 R2 et Lync Server 2013, puis désaffecter le serveur Edge Office Communications Server 2007 R2 avant d’activer la fédération sur le serveur Edge Lync Server 2013. Pour obtenir des détails, consultez les rubriques suivantes :
> <ul>
> <li><p><a href="move-remaining-users-to-lync-server-2013_1.md">Déplacement des autres utilisateurs vers Lync Server 2013</a></p></li>
> <li><p>« Suppression de serveurs et de rôles serveur »à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</a></p></li>
> </ul>


> [!IMPORTANT]  
> Si votre fédération XMPP est acheminée via un serveur Edge Lync Server 2013, les utilisateurs Office Communications Server 2007 R2 hérités ne peuvent pas communiquer avec le partenaire fédéré XMPP tant que tous les utilisateurs n’ont pas été déplacés vers Lync Server 2013, que les stratégies XMPP et les certificats n’ont pas été configurés, que le partenaire fédéré XMPP n’a pas été configuré sur Lync Server 2013, et enfin que les entrées DNS n’ont pas été mises à jour.

Pour pouvoir publier, activer ou désactiver une topologie lorsque vous ajoutez ou supprimez un rôle serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Admins du domaine. Il est également possible de déléguer les autorisations et les droits d’utilisateur voulus pour ajouter des rôles serveur. Pour plus d’informations, reportez-vous à [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) (contenu éventuellement en anglais) dans la documentation relative au déploiement des serveurs Standard Edition ou Enterprise Edition. Pour toutes les autres modifications de configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est requise.

## Pour supprimer l’association de fédération héritée des sites Lync Server 2013

1.  Ouvrez la topologie du premier pool à l’aide du générateur de topologie.

2.  Dans le volet gauche, naviguez jusqu’au nœud du site.

3.  Cliquez avec le bouton droit sur le site, puis cliquez sur **Modifier les propriétés**.

4.  Sélectionnez **Itinéraire de fédération** dans le volet gauche.

5.  Sous Attribution de l’itinéraire de fédération du site, désactivez la case à cocher en regard de l’option **Activer la fédération SIP** pour désactiver l’itinéraire de fédération via le **BackCompatSite**.
    
    ![Boîte de dialogue Modifier les propriétés, Itinéraire de fédération](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, Itinéraire de fédération")

6.  Cliquez sur **OK** pour fermer la page Modifier les propriétés.

7.  Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **Lync Server**.

8.  Dans le menu **Action**, cliquez sur **Publier la topologie** et exécutez l’Assistant.

## Pour configurer le serveur Edge hérité comme serveur Edge non fédéré

1.  Dans le **Générateur de topologie**, dans le menu **Action**, cliquez sur **Fusionner la topologie Office Communications Server 2007 R2**.

2.  Cliquez sur **Suivant** pour continuer.

3.  Dans **Spécifier la configuration Edge**, sélectionnez le **Nom de domaine complet (FQDN) interne de serveur Edge** actuellement configuré pour la fédération, puis cliquez sur **Modification**.
    
    ![Fusionner la topologie OCS 2007 R2, Spécifier la configuration Edge](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Fusionner la topologie OCS 2007 R2, Spécifier la configuration Edge")

4.  Cliquez sur **Suivant** et acceptez les paramètres par défaut jusqu’à ce que vous accédiez à la page **Spécifier la configuration Edge externe**  :
    
    ![Page Spécifier la configuration Edge externe du Générateur de topologie](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Page Spécifier la configuration Edge externe du Générateur de topologie")

5.  Dans **Spécifier la configuration Edge externe**, désactivez la case à cocher **Ce pool de serveurs Edge est utilisé pour la fédération et la solution PIC (Public IM Connectivity)**. Cela supprimera l’association de fédération avec le BackCompatSite.
    
    > [!IMPORTANT]  
    > Cette étape est importante. Vous devez désactiver cette option pour supprimer l’association de fédération héritée.

6.  Cliquez sur **Suivant** et acceptez les paramètres par défaut des pages restantes de l’Assistant.

7.  Dans **Sommaire**, cliquez sur **Suivant** pour commencer à fusionner les topologies.

8.  Dans la colonne **Statut**, vérifiez que la valeur est **Opération réussie**, puis cliquez sur **Terminer** pour fermer l’Assistant.

9.  Dans le menu **Actions**, sélectionnez **Publier la topologie**, puis cliquez sur **Suivant**.

10. Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer.
    
    ![Générateur de topologie avec site affiché après la fusion](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Générateur de topologie avec site affiché après la fusion")
    
    Comme indiqué dans la figure précédente, la **fédération SIP** située sous **Attribution de l’itinéraire de fédération du site** est définie sur **Désactivée**.

## Pour configurer des certificats sur le serveur Edge Lync Server 2013

1.  Exportez le certificat de proxy d’accès externe, avec la clé privée, à partir du serveur Edge Office Communications Server 2007 R2 hérité.

2.  Sur le serveur Edge Lync Server 2013, importez le certificat externe de proxy d’accès à partir de l’étape précédente.

3.  Attribuez le certificat externe de proxy d’accès à l’interface externe Lync Server 2013 du serveur Edge.

4.  Le certificat de l’interface interne du serveur Edge Lync Server 2013 ne doit pas être modifié.

## Pour changer l’itinéraire de fédération Office Communications Server 2007 R2 afin d’utiliser le serveur Edge Lync Server 2013

1.  Sur le serveur Standard Edition ou le serveur frontalOffice Communications Server 2007 R2, ouvrez les outils d’administration Office Communications Server 2007 R2.

2.  Dans le volet gauche, développez le nœud supérieur, puis cliquez avec le bouton droit sur le nœud **Forêt**. Sélectionnez **Propriétés**, puis cliquez sur **Propriétés globales**.

3.  Cliquez sur l’onglet **Fédération**.

4.  Activez la case à cocher pour activer la fédération et la solution PIC (Public IM Connectivity).

5.  Entrez le nom de domaine complet (FQDN) du serveur Edge  Lync Server 2013, puis cliquez sur **OK**.
    
    ![Propriétés globales OCS Global, onglet Fédération](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Propriétés globales OCS Global, onglet Fédération")

## Pour activer la fédération du serveur Edge Lync Server 2013

1.  Dans le générateur de topologie, naviguez jusqu’au nœud **Edge pools** Lync Server 2013.

2.  Développez le nœud, cliquez avec le bouton droit sur le serveur Edge répertorié, puis cliquez sur **Modifier les propriétés**.
    
    > [!NOTE]  
    > La fédération ne peut être activée que pour un seul pool de serveurs Edge. Si vous avez plusieurs pools Edge, sélectionnez-en un à utiliser comme pool de serveurs Edge de fédération.

3.  Dans la page **Général**, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**.
    
    ![Modifier les propriétés, Général, Activer la fédération Edge](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Modifier les propriétés, Général, Activer la fédération Edge")

4.  Cliquez sur **OK** pour fermer la page Modifier les propriétés.

5.  Naviguez ensuite vers le nœud du site.

6.  Cliquez avec le bouton droit sur le site, puis cliquez sur **Modifier les propriétés**.

7.  Dans le volet gauche, cliquez sur **Itinéraire de fédération**.

8.  Sous **Attribution de l’itinéraire de fédération du site**, sélectionnez **Activer la fédération SIP** puis, dans la liste, sélectionnez le serveur EdgeLync Server 2013 répertorié.

9.  Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.
    
    ![Modifier les propriétés, Général, Pool de serveurs Edge associé](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Modifier les propriétés, Général, Pool de serveurs Edge associé")
    
    Pour les déploiements sur plusieurs sites, effectuez cette procédure sur chaque site.

## Pour configurer le chemin d’accès sortant des médias Lync Server 2013, serveur Edge

1.  Dans le **Générateur de topologie**, naviguez jusqu’au pool Lync Server 2013 sous **Serveur frontaux Standard Edition** ou **Pools frontaux Enterprise Edition**.

2.  Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.

3.  Dans la section **Associations**, activez la case à cocher **Associer un pool Edge (pour les composants multimédias)**.

4.  Dans le menu déroulant, sélectionnez le serveur Edge Lync Server 2013.
    
    ![Boîte de dialogue Modifier les propriétés, Pool Edge associé](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, Pool Edge associé")

5.  Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.

## Pour publier les modifications de configuration du serveur Edge

1.  Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **Lync Server**.

2.  Dans le menu **Action**, sélectionnez **Publier la topologie** et exécutez l’Assistant.

3.  Attendez que la réplication Active Directory se produise sur tous les pools de serveurs impliqués dans le déploiement.
    
    > [!NOTE]  
    > Vous pouvez voir le message suivant :<br />
    <strong>Attention : La topologie contient plusieurs serveurs Edge fédérés. Cela peut se produire au cours d’une migration vers une version plus récente du produit. Dans ce cas, un seul serveur Edge serait utilisé activement pour la fédération. Vérifiez que l’enregistrement SRV DNS externe pointe vers le serveur Edge voulu. Si vous voulez déployer plusieurs serveurs Edge de fédération de sorte qu’ils soient actifs simultanément (pas un scénario de migration, donc), vérifiez que tous les partenaires fédérés utilisent Office Communications Server 2007 R2 ou Lync Server. Vérifiez que l’enregistrement SRV DNS externe liste tous les serveurs Edge activés pour la fédération.</strong><br />
    Cet avertissement est attendu et peut être ignoré en toute sécurité.

## Pour vérifier la fédération et l’accès à distance pour les utilisateurs externes

1.  Dans le serveur frontal Lync Server 2013, ouvrez Lync Server Management Shell.

2.  Pour vérifier l’état de la fédération et de l’accès à distance, dans la ligne de commande, tapez ceci :
    
        Get-CsAccessEdgeConfiguration

3.  Pour activer la fédération et l’accès à distance, dans la ligne de commande, tapez ceci :
    
        Set-CsAccessEdgeConfiguration
    
    Pour plus d’informations sur ces applets de commande, reportez-vous aux rubriques suivantes : [Get-CsAccessEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAccessEdgeConfiguration) et [Set-CsAccessEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAccessEdgeConfiguration) (contenu éventuellement en anglais).

4.  Attendez que la réplication soit terminée avant de mettre les serveurs Edge Lync Server 2013 en ligne et de tester la fédération et l’accès externe.

## Pour configurer le serveur Edge Lync Server 2013

1.  Mettez tous les serveurs Edge Lync Server 2013 en ligne.

2.  Mettez à jour les règles de routage du pare-feu externe ou les paramètres du programme d’équilibrage de la charge matérielle pour envoyer le trafic SIP pour l’accès externe (port 443, en général) et la fédération (port 5061, en général) au serveur Edge  Lync Server 2013, au lieu du serveur serveur Edge hérité.
    
    > [!NOTE]  
    > Si vous n’avez pas de programme d’équilibrage de la charge matérielle, vous devez mettre à jour l’enregistrement DNS A pour que la fédération résolve le nouveau serveur Edge d’accès Lync Server. Pour effectuer cette action avec un minimum de perturbations, diminuez la valeur TTL pour le nom de domaine (FQDN) Edge d’accès Lync Server externe, de sorte que lors de la mise à jour de DNS pour pointer vers le nouveau serveur Edge d’accès Lync Server, la fédération et l’accès à distance soient rapidement mis à jour.

3.  Arrêtez ensuite le **serveur Edge d’accès Lync Server** sur chaque ordinateur serveur Edge.

4.  Sur chaque ordinateur serveur Edge hérité, ouvrez l’applet **Services** dans les **Outils d’administration**.

5.  Dans la liste des services, recherchez **Serveur Edge d’accès Office Communications Server**.

6.  Cliquez avec le bouton droit sur le nom du service, puis sélectionnez **Arrêter** pour arrêter le service.

7.  Définissez le type de démarrage sur **Désactivé**.

8.  Cliquez sur **OK** pour fermer la fenêtre **Propriétés**.

## Pour tester la connectivité des utilisateurs externes et de l’accès externe

  - Utilisateurs d’au moins un domaine fédéré, un utilisateur interne sur Lync Server 2013 et un utilisateur sur Office Communications Server 2007 R2. Testez la messagerie instantanée (IM), la présence, l’audio/vidéo (A/V) et le partage de Bureau.

  - Utilisateurs de chaque fournisseur de service de messagerie instantanée public que votre entreprise prend en charge (et dont la configuration a été effectuée) en communiquant avec un utilisateur sur Lync Server 2013 et un utilisateur sur Office Communications Server 2007 R2.

  - Vérifiez que les utilisateurs anonymes peuvent participer à des conférences.

  - Utilisateur hébergé sur Office Communications Server 2007 R2 utilisant l’accès utilisateur à distance (en se connectant à Office Communications Server 2007 R2 en dehors de l’intranet mais sans VPN) avec un utilisateur sur Lync Server 2013 et un utilisateur sur Office Communications Server 2007 R2. Testez la messagerie instantanée (IM), la présence, l’audio/vidéo (A/V) et le partage de Bureau.

  - Utilisateur hébergé sur Lync Server 2013 utilisant l’accès utilisateur à distance (en se connectant à Lync Server 2013 en dehors de l’intranet mais sans VPN) avec un utilisateur sur Lync Server 2013 et un utilisateur sur Office Communications Server 2007 R2. Testez la messagerie instantanée (IM), la présence, l’audio/vidéo (A/V) et le partage de Bureau.

