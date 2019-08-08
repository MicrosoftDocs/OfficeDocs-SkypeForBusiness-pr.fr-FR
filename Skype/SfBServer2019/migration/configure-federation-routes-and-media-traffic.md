---
title: Configuration des itinéraires de fédération et du trafic multimédia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: La Fédération est une relation d’approbation entre au moins deux domaines SIP, qui permet aux utilisateurs d’organisations distinctes de communiquer au sein des frontières du réseau. Après avoir effectué une migration vers votre pool de pilotes, vous devez effectuer une transition de l’itinéraire de Fédération de vos serveurs de périphérie de version précédente vers l’itinéraire de Fédération de vos serveurs Edge 2019 Skype entreprise Server.
ms.openlocfilehash: 50c10a4dced237e59c8dad12b5bdee1ef7d970fe
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239361"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configuration des itinéraires de fédération et du trafic multimédia

La Fédération est une relation d’approbation entre au moins deux domaines SIP, qui permet aux utilisateurs d’organisations distinctes de communiquer au sein des frontières du réseau. Après avoir effectué une migration vers votre pool de pilotes, vous devez passer de l’itinéraire de Fédération des serveurs Edge de votre version précédente à l’itinéraire de Fédération de vos serveurs de périmètre Skype entreprise Server 2019.
  
Pour effectuer un déploiement sur un site, procédez comme suit pour basculer entre l’itinéraire de la Fédération et l’itinéraire du trafic multimédia du serveur Edge et du 2019 directeur de votre version précédente.
  
> [!IMPORTANT]
> La modification de l’itinéraire de Fédération et du trafic multimédia nécessite que vous planifiiez des arrêts de maintenance pour le serveur Skype entreprise Server 2019 et la version latérale antérieure. Ce processus de transition complet signifie également que l’accès fédéré ne sera pas disponible pendant la durée de la période d’interruption. Nous vous conseillons de planifier le temps d’arrêt à un moment où vous vous attendez à un minimum d’activités utilisateur. Vous devez également fournir une notification suffisante à vos utilisateurs finaux. Planifiez en conséquence pour cette interruption et définissez les attentes appropriées au sein de votre organisation. 
  
> [!IMPORTANT]
> Si votre serveur de bord antérieur est configuré pour utiliser le même nom de domaine complet pour le service Edge d’accès, le service Edge de conférence Web et le service Edge A/V, les procédures de cette section ne sont pas prises en charge. Si les services Edge hérités sont configurés pour utiliser le même nom de domaine complet (FQDN), vous devez tout d’abord migrer tous vos utilisateurs, puis désactivez le serveur Edge versions antérieur avant d’activer la Fédération sur le serveur Edge 2019 Skype entreprise Server. 
  
> [!IMPORTANT]
> Si votre Fédération XMPP est routée par le biais d’un serveur Edge Skype entreprise Server 2019, les utilisateurs de la version précédente ne seront pas en mesure de communiquer avec le partenaire fédéré de XMPP tant que tous les utilisateurs n’ont pas été déplacés vers Skype entreprise Server 2019 et les stratégies XMPP et des certificats ont été configurés, le partenaire fédéré de XMPP a été configuré sur Skype entreprise Server 2019 et, enfin, les entrées DNS ont été mises à jour. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>Pour supprimer l’Association de Fédération héritée des sites 2019 de Skype entreprise Server

1. Sur le serveur frontal Skype entreprise Server 2019, ouvrez la topologie existante dans le générateur de topologie. 
    
2. Dans le volet gauche, accédez au nœud de site qui se trouve juste en dessous de **Skype entreprise Server**.
    
3. Cliquez avec le bouton droit sur le site, puis cliquez sur **modifier les propriétés**.
    
4. Dans le volet gauche, sélectionnez **gamme de Fédération**. 
    
5. Sous **affectation**de l’itinéraire de Fédération de site, décochez la case **activer la Fédération SIP** pour désactiver le routage de Fédération par le biais de l’environnement hérité. 
  
6. Cliquez sur **OK** pour fermer la page modifier les propriétés. 
    
7. Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **Skype entreprise Server**.
    
8. Dans le menu **action** , cliquez sur **publier la topologie**.
    
9. Cliquez sur **suivant** pour finaliser le processus de publication, puis cliquez sur **Terminer** lorsque le processus de publication est terminé. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Pour configurer le serveur de périphérie traditionnel en tant que serveur Edge non fédéré

1. Dans le volet gauche, accédez au nœud d’installation hérité, puis au nœud de pools de **périphérie** . 
    
2. Cliquez avec le bouton droit sur le serveur Edge, puis cliquez sur **modifier les propriétés**.
    
3. Dans le volet gauche, sélectionnez **général** . 
    
4. Décochez la case **activer la Fédération pour ce pool Edge (port 5061)** et sélectionnez **OK** pour fermer la page. 
  
5. Dans le menu **action** , cliquez sur **publier la topologie**, puis sur **suivant**.
    
6. Lorsque l' **Assistant Publication** est terminé, cliquez sur **Terminer** pour fermer l’Assistant. 
    
7. Vérifiez que la Fédération du serveur Edge héritée est désactivée dans le générateur de topologie.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>Pour configurer des certificats sur le serveur Edge hérité

1. Exportez le certificat de proxy d’accès externe, avec la clé privée, à partir du serveur Edge hérité. 
    
2. Sur le serveur Edge 2019 de Skype entreprise Server, puis importez le certificat externe de proxy d’accès à partir de l’étape précédente.
    
3. Affectez le certificat externe du proxy d’accès à l’interface externe de Skype entreprise Server 2019 du serveur Edge.
    
4. Le certificat d’interface interne du serveur Edge 2019 de Skype entreprise Server doit être demandé auprès d’une autorité de certification approuvée et attribué. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>Pour modifier l’itinéraire de Fédération de la version précédente pour utiliser Skype entreprise Server 2019 Edge Server

1. Dans le générateur de topologie, dans le volet gauche, accédez au nœud **Skype entreprise Server 2019** , puis au nœud Pools de **périphérie** . 
    
2. Cliquez avec le bouton droit sur le serveur Edge, puis cliquez sur **modifier les propriétés**.
    
3. Dans le volet gauche, sélectionnez **général** . 
    
4. Activez la case à cocher **activer la Fédération pour ce pool Edge (port 5061)**, puis cliquez sur **OK** pour fermer la page. 
  
5. Dans le menu **action** , cliquez sur **publier la topologie**, puis sur **suivant**.
    
6. Lorsque l' **Assistant Publication** est terminé, cliquez sur **Terminer** pour fermer l’Assistant. 
    
7. Vérifiez que la **Fédération (port 5061)** est définie sur **activée** dans le générateur de topologie.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>Pour mettre à jour Skype entreprise Server 2019 Edge Server Federation Next tronçon

1. Dans le générateur de topologie, dans le volet gauche, accédez au nœud **Skype entreprise Server 2019** , puis au nœud Pools de **périphérie** . 
    
2. Développez le nœud, cliquez avec le bouton droit sur le serveur Edge indiqué, puis cliquez sur **modifier les propriétés**. 
    
3. Dans la page **général** , sous **sélection du tronçon suivant**, sélectionnez dans la liste déroulante le pool Skype entreprise Server 2019.
  
4. Cliquez sur **OK** pour fermer la page modifier les propriétés. 
    
5. Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **Skype entreprise Server**. 
    
6. Dans le menu **action** , cliquez sur **publier la topologie** et terminer l’Assistant. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>Pour configurer le chemin multimédia sortant du serveur Microsoft Skype entreprise Server 2019 Edge

1. Dans le concepteur de topologies, dans le volet gauche, accédez au nœud **Skype entreprise Server 2019** , puis au pool sous **Standard Edition serveurs front end** ou **Enterprise Edition**.
    
2. Cliquez avec le bouton droit sur la liste, puis cliquez sur **modifier les propriétés**.
    
3. Dans la section **associations** , activez la case à cocher **associer le pool Edge (pour les composants multimédias)** . 
  
4. Dans la liste déroulante, sélectionnez le serveur Edge 2019 de Skype entreprise Server.
    
5. Cliquez sur **OK** pour fermer la page **modifier les propriétés** . 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>Pour activer Skype entreprise Server 2019 Edge Server Federation

1. Dans le générateur de topologie, dans le volet gauche, accédez au nœud **Skype entreprise Server 2019** , puis au nœud Pools de **périphérie** . 
    
2. Développez le nœud, cliquez avec le bouton droit sur le serveur Edge indiqué, puis cliquez sur **modifier les propriétés**. 
    
    > [!NOTE]
    > La Fédération ne peut être activée que pour un seul pool de bords. Si vous avez plusieurs pools de bords, sélectionnez-en un pour les utiliser comme pools de frontière de Fédération. 
  
3. Dans la page **général** , vérifiez que la case à cocher **activer la Fédération pour ce pool Edge (port 5061)** est activée. 
  
4. Cliquez sur **OK** pour fermer la page modifier les propriétés. 
    
5. Accédez au nœud site. 
    
6. Cliquez avec le bouton droit sur le site, puis cliquez sur **modifier les propriétés**.
    
7. Dans le volet de gauche, cliquez sur **route de Fédération**.
    
8. Sous **affectation**de l’itinéraire de la Fédération de sites, sélectionnez **activer la Fédération SIP**, puis dans la liste, sélectionnez le serveur Edge 2019 de Skype entreprise Server. 
  
9. Cliquez sur **OK** pour fermer la page **modifier les propriétés** . 
    
     Pour les déploiements multisites, procédez comme suit sur chaque site. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>Pour publier les modifications de configuration de serveur Edge

1. Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **Skype entreprise Server**. 
    
2. Dans le menu **action** , sélectionnez **publier la topologie** et terminer l’Assistant. 
    
3. Attendez la fin de la réplication Active Directory pour tous les pools du déploiement.
    
    > [!NOTE]
    > Le message suivant risque de s’afficher: **Avertissement: la topologie comporte plusieurs serveurs Edge fédérés. Cela peut se produire lors de la migration vers une version plus récente du produit. Dans ce cas, un seul serveur Edge serait utilisé activement pour la Fédération. Vérifiez que l’enregistrement SRV DNS externe pointe vers le serveur Edge approprié. Si vous voulez déployer plusieurs serveurs de frontière de Fédération de manière à être actifs en même temps (il ne s’agit pas d’un scénario de migration), vérifiez que tous les partenaires fédérés utilisent Skype entreprise Server. Vérifiez que l’enregistrement SRV DNS externe recense tous les serveurs Edge compatibles avec la Fédération.** Cet avertissement est attendu et peut être ignoré en toute sécurité. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>Pour configurer Skype entreprise Server 2019 Edge Server

1. Accédez à tous les serveurs Edge Skype entreprise Server 2019 en ligne. 
    
2. Mettez à jour les règles de routage de pare-feu externe ou les paramètres de l’équilibrage de charge matérielle pour envoyer le trafic SIP pour l’accès externe (généralement le port 443) et la Fédération (généralement port 5061) vers le serveur Edge Skype entreprise Server 2019, au lieu du serveur Edge hérité.
    
    > [!NOTE]
    > Si vous n’avez pas d’équilibrage de charge matérielle, vous devez mettre à jour l’enregistrement DNS A pour la Fédération pour résoudre le nouveau serveur de périphérie de Skype entreprise Server. Pour effectuer cette opération avec un minimum de perturbation, réduisez la valeur TLL du nom de domaine complet (FQDN) du périmètre du serveur Skype entreprise externe, de sorte que lorsque DNS est mis à jour de manière à ce qu’il pointe vers le nouveau serveur Skype entreprise Server Access, la Fédération et l’accès à distance seront mis à jour rapidement. 
  
3. Arrêtez l' **accès à Skype entreprise Server** depuis chaque ordinateur du serveur Edge. 
    
4. À partir de chaque ordinateur serveur Edge hérité, ouvrez l’application **services** à partir des **Outils d’administration**.
    
5. Dans la liste services, recherchez **Edge Access pour Skype entreprise Server**.
    
6. Cliquez avec le bouton droit sur le nom des services, puis sélectionnez **arrêter** pour arrêter le service. 
    
7. Définissez le type de démarrage sur **désactivé**. 
    
8. Cliquez sur **OK** pour fermer la fenêtre **Propriétés** . 
    

