---
title: Configuration des itinéraires de fédération et du trafic multimédia
TOCTitle: Configuration des itinéraires de fédération et du trafic multimédia
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49891428
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des itinéraires de fédération et du trafic multimédia

 

_**Dernière rubrique modifiée :** 2012-10-15_

La fédération est une relation d’approbation entre deux ou plusieurs domaines SIP qui permet aux utilisateurs d’entreprises distinctes de communiquer au-delà des limites du réseau. Après avoir effectué la migration vers votre premier pool Lync Server 2013, vous devez effectuer une transition de l’itinéraire de la fédération de vos serveurs Edge Lync Server 2010 vers l’itinéraire de fédération de vos serveurs Edge Lync Server 2013.

Utilisez les procédures suivantes pour effectuer la transition de l’itinéraire de fédération et de l’itinéraire de trafic multimédia de votre serveur Edge et directeur Lync Server 2010 vers votre serveur Edge Lync Server 2013, pour un déploiement sur un seul site.

> [!IMPORTANT]  
> La modification de l’itinéraire de fédération et de l’itinéraire de trafic multimédia nécessite que vous planifiiez une interruption de maintenance pour les serveurs Edge Lync Server 2013 et Lync Server 2010. Ce processus de transition signifie également que l’accès fédéré sera indisponible pendant la durée de l’interruption. Vous devez donc planifier cette interruption à un moment où l’activité des utilisateurs sera minimale. Prévoyez aussi d’en informer les utilisateurs finaux suffisamment à l’avance. Anticipez cette interruption à tous les niveaux et informez-en votre entreprise afin qu’elle s’y prépare en conséquence.

> [!IMPORTANT]  
> Si votre serveur Edge Lync Server 2010 hérité est configuré pour utiliser le même FQDN pour le serveur Edge d’accès, le service Edge de conférence et le service Edge A/V, les procédures de cette section ne sont pas prises en charge. Si les services Edge hérités sont configurés pour utiliser le même FQDN, vous devez tout d’abord migrer tous les utilisateurs de Lync Server 2010 vers Lync Server 2013, puis supprimer le serveur Edge Lync Server 2010 avant d’activer la fédération sur le serveur Edge Lync Server 2013.

> [!IMPORTANT]  
> Si votre fédération XMPP est acheminée via un serveur Edge Lync Server 2013, les utilisateurs Lync Server 2010 hérités ne peuvent pas communiquer avec le partenaire fédéré XMPP tant que tous les utilisateurs n’ont pas été déplacés vers Lync Server 2013, que les stratégies XMPP et les certificats n’ont pas été configurés, que le partenaire fédéré XMPP n’a pas été configuré sur Lync Server 2013, et enfin que les entrées DNS n’ont pas été mises à jour.

## Pour supprimer l’association de fédération héritée des sites Lync Server 2013

1.  Sur le serveur frontal Lync Server 2013, ouvrez la topologie existante dans le générateur de topologie.

2.  Dans le volet gauche, accédez au nœud du site, situé directement sous **Lync Server**.

3.  Cliquez avec le bouton droit sur le site, puis cliquez sur **Modifier les propriétés** .

4.  Dans le volet gauche, sélectionnez **Itinéraire de fédération** .

5.  Sous **Attribution de l’itinéraire de fédération du site**, décochez la case **Activer la fédération SIP** pour désactiver l’itinéraire de fédération via l’environnement Lync Server 2010 hérité.
    
    ![Boîte de dialogue Modifier les propriétés, page Itinéraire de fédération](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page Itinéraire de fédération")

6.  Cliquez sur **OK** pour fermer la page Modifier les propriétés.

7.  Dans le **Générateur de topologie** , sélectionnez le nœud supérieur **Lync Server** .

8.  Dans le menu **Action** , cliquez sur **Publier la topologie** .

9.  Cliquez sur **Suivant** pour terminer le processus de publication, puis cliquez sur **Terminer** quand la publication est terminée.

## Pour configurer le serveur Edge hérité comme serveur Edge non fédéré

1.  Dans le volet gauche, accédez au nœud **Lync Server 2010**, puis au nœud **Pool de serveurs Edge**.

2.  Cliquez avec le bouton droit sur le serveur Edge, puis cliquez sur **Modifier les propriétés** .

3.  Sélectionnez **Général** dans le volet gauche.

4.  Décochez la case **Activer la fédération pour ce pool Edge (port 5061)** et sélectionnez **OK** pour fermer la page.
    
    ![Modifier les propriétés, Général, effacer Activer la fédération](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Modifier les propriétés, Général, effacer Activer la fédération")

5.  Dans le menu **Actions** , sélectionnez **Publier la topologie** , puis cliquez sur **Suivant** .

6.  Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer.

7.  Vérifiez que la fédération pour le serveur Edge hérité est désactivée.
    
    ![Générateur de topologie, pool Edge, Fédération désactivée](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Générateur de topologie, pool Edge, Fédération désactivée")

## Pour configurer des certificats sur le serveur Edge Lync Server 2010

1.  Exportez le certificat de proxy d’accès externe, avec la clé privée, à partir du serveur Edge Lync Server 2010 hérité.

2.  Sur le serveur Edge Lync Server 2013, importez le certificat externe de proxy d’accès à partir de l’étape précédente.

3.  Attribuez le certificat externe de proxy d’accès à l’interface externe Lync Server 2013 du serveur Edge.

4.  Le certificat d’interface interne du serveur Edge Lync Server 2013 doit être demandé à partir d’une autorité de certification approuvée et affecté.

## Pour changer l’itinéraire de fédération Lync Server 2010 pour utiliser un serveur Edge Lync Server 2013

1.  Dans le volet gauche du générateur de topologie, accédez au nœud **Lync Server 2013**, puis au nœud **Pool de serveurs Edge**.

2.  Cliquez avec le bouton droit sur le serveur Edge, puis cliquez sur **Modifier les propriétés** .

3.  Sélectionnez **Général** dans le volet gauche.

4.  Cochez la case **Activer la fédération pour ce pool Edge (port 5061)** , puis cliquez sur **OK** pour fermer la page.
    
    ![Boîte de dialogue Modifier les propriétés, page Général](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page Général")

5.  Dans le menu **Actions** , sélectionnez **Publier la topologie** , puis cliquez sur **Suivant** .

6.  Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer.

7.  Vérifiez que **Fédération (port 5061)** est **Activé**.
    
    ![Générateur de topologie, pool Edge, Fédération activée](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Générateur de topologie, pool Edge, Fédération activée")

## Pour mettre à jour le tronçon suivant de fédération du serveur Edge Lync Server 2013

1.  Dans le volet gauche du générateur de topologie, accédez au nœud **Lync Server 2013**, puis au nœud **Pool de serveurs Edge**.

2.  Développez le nœud, cliquez avec le bouton droit sur le serveur Edge listé, puis cliquez sur **Modifier les propriétés** .

3.  Dans la page **Général** , sous **Sélection du tronçon suivant** , sélectionnez le pool Lync Server 2013  dans la liste déroulante.
    
    ![Boîte de dialogue Modifier les propriétés, page Tronçon suivant](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page Tronçon suivant")

4.  Cliquez sur **OK** pour fermer la page Modifier les propriétés.

5.  Dans le **Générateur de topologie** , sélectionnez le nœud supérieur **Lync Server** .

6.  Dans le menu **Action** , cliquez sur **Publier la topologie** et exécutez l’Assistant.

## Pour configurer le chemin d’accès sortant des médias Lync Server 2013, serveur Edge

1.  Dans le générateur de topologie, dans le volet gauche, accédez au nœud **Lync Server 2013**, puis au pool sous **Serveurs frontaux Standard Edition** ou **Pools frontaux Enterprise Edition** .

2.  Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés** .

3.  Dans la section **Associations** , activez la case à cocher **Pool Edge associé (pour composants médias)** .
    
    ![Modifier les propriétés, Général, Pool de serveurs Edge associé](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Modifier les propriétés, Général, Pool de serveurs Edge associé")

4.  Dans le menu déroulant, sélectionnez le serveur Edge Lync Server 2013.

5.  Cliquez sur **OK** pour fermer la page **Modifier les propriétés** .

## Pour activer la fédération du serveur Edge Lync Server 2013

1.  Dans le volet gauche du générateur de topologie, accédez au nœud **Lync Server 2013**, puis au nœud **Pool de serveurs Edge**.

2.  Développez le nœud, cliquez avec le bouton droit sur le serveur Edge répertorié, puis cliquez sur **Modifier les propriétés** .
    
    > [!NOTE]  
    > La fédération ne peut être activée que pour un seul pool de serveurs Edge. Si vous avez plusieurs pools Edge, sélectionnez-en un à utiliser comme pool de serveurs Edge de fédération.

3.  Dans la page **Général** , vérifiez que le paramètre **Activer la fédération pour ce pool Edge (port 5061)** est coché.
    
    ![Boîte de dialogue Modifier les propriétés, page Général](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page Général")

4.  Cliquez sur **OK** pour fermer la page Modifier les propriétés.

5.  Naviguez ensuite vers le nœud du site.

6.  Cliquez avec le bouton droit sur le site, puis cliquez sur **Modifier les propriétés** .

7.  Dans le volet gauche, cliquez sur **Itinéraire de fédération** .

8.  Sous **Attribution de l’itinéraire de fédération du site** , sélectionnez **Activer la fédération SIP** puis, dans la liste, sélectionnez le serveur EdgeLync Server 2013 répertorié.
    
    ![Modifier les propriétés, page Itinéraire de fédération](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Modifier les propriétés, page Itinéraire de fédération")

9.  Cliquez sur **OK** pour fermer la page **Modifier les propriétés** .
    
    Pour les déploiements sur plusieurs sites, effectuez cette procédure sur chaque site.

## Pour publier les modifications de configuration du serveur Edge

1.  Dans le **Générateur de topologie** , sélectionnez le nœud supérieur **Lync Server** .

2.  Dans le menu **Action** , sélectionnez **Publier la topologie** et exécutez l’Assistant.

3.  Attendez que la réplication Active Directory se produise sur tous les pools de serveurs impliqués dans le déploiement.
    
    > [!NOTE]  
    > Vous pouvez voir le message suivant :<br />
    <strong>Attention : La topologie contient plusieurs serveurs Edge fédérés. Cela peut se produire au cours d’une migration vers une version plus récente du produit. Dans ce cas, un seul serveur Edge serait utilisé activement pour la fédération. Vérifiez que l’enregistrement SRV DNS externe pointe vers le serveur Edge voulu. Si vous voulez déployer plusieurs serveurs Edge de fédération de sorte qu’ils soient actifs simultanément (pas un scénario de migration, donc), vérifiez que tous les partenaires fédérés utilisent Lync Server. Vérifiez que l’enregistrement SRV DNS externe liste tous les serveurs Edge activés pour la fédération.</strong><br />
    Cet avertissement est attendu et peut être ignoré en toute sécurité.

## Pour configurer le serveur Edge Lync Server 2013

1.  Mettez tous les serveurs Edge Lync Server 2013 en ligne.

2.  Mettez à jour les règles de routage du pare-feu externe ou les paramètres du programme d’équilibrage de la charge matérielle pour envoyer le trafic SIP pour l’accès externe (port 443, en général) et la fédération (port 5061, en général) au serveur Edge  Lync Server 2013, au lieu du serveur serveur Edge hérité.
    
    > [!NOTE]  
    > Si vous n’utilisez pas un équilibreur de charge matérielle, vous devez mettre à jour l’enregistrement A DNS pour que la fédération puisse résoudre le nouveau serveur Edge d’accès Lync Server. Pour ce faire, réduisez la valeur TLL pour le FQDN du serveur Edge d’accès Lync Server externe afin que lorsque le DNS est mis à jour pour pointer vers le nouveau serveur Edge d’accès Lync Server, la fédération et l’accès à distance soient mis à jour rapidement.

3.  Ensuite, arrêtez le **Serveur Edge d’accès Lync Server** sur chaque ordinateur de serveur Edge.

4.  Sur chaque ordinateur serveur Edge hérité, ouvrez l’applet **Services** dans les **Outils d’administration** .

5.  Dans la liste des services, trouvez **Serveur Edge d’accès Lync Server** .

6.  Cliquez avec le bouton droit sur le nom du service, puis sélectionnez **Arrêter** pour arrêter le service.

7.  Définissez le type de démarrage sur **Désactivé** .

8.  Cliquez sur **OK** pour fermer la fenêtre **Propriétés** .

