---
title: Configurer les itinéraires de fédération et le trafic multimédia
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La fédération est une relation d’approbation entre deux ou plusieurs domaines SIP qui permet aux utilisateurs d’organisations distinctes de communiquer au-delà des limites des réseaux. Une fois que vous avez effectué la migration vers votre pool pilote, vous devez effectuer une transition de l’itinéraire de Fédération de vos serveurs Edge de versions précédentes vers l’itinéraire de Fédération de vos serveurs Edge Skype entreprise Server 2019.
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754034"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configurer les itinéraires de fédération et le trafic multimédia

La fédération est une relation d’approbation entre deux ou plusieurs domaines SIP qui permet aux utilisateurs d’organisations distinctes de communiquer au-delà des limites des réseaux. Une fois que vous avez effectué la migration vers votre pool pilote, vous devez passer de l’itinéraire de Fédération de vos serveurs Edge de la version précédente à l’itinéraire de Fédération de vos serveurs Edge Skype entreprise Server 2019.
  
Utilisez les procédures suivantes pour effectuer la transition de l’itinéraire de Fédération et de l’itinéraire de trafic multimédia depuis le serveur Edge et le directeur de votre version précédente vers votre serveur Edge Skype entreprise Server 2019, pour un déploiement sur un seul site.
  
> [!IMPORTANT]
> Le changement de l’itinéraire de Fédération et de l’itinéraire de trafic multimédia nécessite de planifier le temps d’arrêt de la maintenance pour les serveurs Edge Skype entreprise Server 2019 et version précédente. Ce processus de transition signifie également que l’accès fédéré sera indisponible pendant la durée de l’interruption. Vous devez donc planifier cette interruption à un moment où l’activité des utilisateurs sera minimale. Prévoyez aussi d’en informer les utilisateurs finaux suffisamment à l’avance. Anticipez cette interruption à tous les niveaux et informez-en votre organisation afin qu’elle s’y prépare en conséquence. 
  
> [!IMPORTANT]
> Si votre serveur Edge hérité est configuré pour utiliser le même nom de domaine complet pour le service Edge d’accès, le service Edge de conférence Web et le service Edge A/V, les procédures décrites dans cette section ne sont pas prises en charge. Si les services Edge hérités sont configurés pour utiliser le même nom de domaine complet, vous devez d’abord migrer tous vos utilisateurs, puis désactivez le serveur Edge des versions précédentes avant d’activer la Fédération sur le serveur Edge de Skype entreprise Server 2019. 
  
> [!IMPORTANT]
> Si votre Fédération XMPP est acheminée via un serveur Edge Skype entreprise Server 2019, les utilisateurs de la version précédente ne seront pas en mesure de communiquer avec le partenaire fédéré XMPP tant que tous les utilisateurs n’ont pas été déplacés vers Skype entreprise Server 2019, que les stratégies XMPP et les certificats ont été configurés, le partenaire fédéré XMPP a été configuré sur Skype entreprise Server 2019 et, enfin, les entrées DNS ont été mises à jour. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>Pour supprimer l’Association de Fédération héritée des sites Skype entreprise Server 2019

1. Sur le serveur frontal Skype entreprise Server 2019, ouvrez la topologie existante dans le générateur de topologie. 
    
2. Dans le volet de gauche, accédez au nœud de site, qui se trouve directement sous **Skype entreprise Server**.
    
3. Cliquez avec le bouton droit sur le site, puis cliquez sur **Modifier les propriétés**.
    
4. Dans le volet gauche, sélectionnez **Itinéraire de fédération**. 
    
5. Sous **attribution**de l’itinéraire de Fédération du site, désactivez la case à cocher **activer la Fédération SIP** pour désactiver l’itinéraire de Fédération dans l’environnement hérité. 
  
6. Cliquez sur **OK** pour fermer la page Modifier les propriétés. 
    
7. Dans le **Générateur de topologies**, sélectionnez le nœud supérieur **Skype entreprise Server**.
    
8. Dans le menu **Action**, cliquez sur **Publier la topologie**.
    
9. Cliquez sur **suivant** pour terminer le processus de publication, puis cliquez sur **Terminer** lorsque le processus de publication est terminé. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Pour configurer le serveur Edge hérité en tant que serveur Edge non-fédérant

1. Dans le volet gauche, accédez au nœud installation héritée, puis au nœud **pool** de serveurs Edge. 
    
2. Cliquez avec le bouton droit sur le serveur Edge, puis cliquez sur **Modifier les propriétés**.
    
3. Sélectionnez **Général** dans le volet gauche. 
    
4. Désactivez la case à cocher **activer la Fédération pour ce pool Edge (port 5061)** et sélectionnez **OK** pour fermer la page. 
  
5. Dans le menu **Action**, sélectionnez **Publier la topologie**, puis cliquez sur **Suivant**.
    
6. Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer. 
    
7. Vérifiez que la Fédération pour le serveur Edge hérité est désactivée dans le générateur de topologie.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>Pour configurer des certificats sur le serveur Edge hérité

1. Exportez le certificat de proxy d’accès externe, avec la clé privée, à partir du serveur Edge hérité. 
    
2. Sur le serveur Edge de Skype entreprise Server 2019, puis importez le certificat externe de proxy d’accès à partir de l’étape précédente.
    
3. Affectez le certificat externe de proxy d’accès à l’interface externe Skype entreprise Server 2019 du serveur Edge.
    
4. Le certificat d’interface interne du serveur Edge de Skype entreprise Server 2019 doit être demandé auprès d’une autorité de certification approuvée et affecté. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>Pour modifier l’itinéraire de Fédération de la version précédente afin d’utiliser le serveur Edge de Skype entreprise Server 2019

1. À partir du générateur de topologie, dans le volet gauche, accédez au nœud **Skype entreprise Server 2019** , puis au nœud **pool** de serveurs Edge. 
    
2. Cliquez avec le bouton droit sur le serveur Edge, puis cliquez sur **Modifier les propriétés**.
    
3. Sélectionnez **Général** dans le volet gauche. 
    
4. Activez la case à cocher **activer la Fédération pour ce pool Edge (port 5061)**, puis cliquez sur **OK** pour fermer la page. 
  
5. Dans le menu **Action**, sélectionnez **Publier la topologie**, puis cliquez sur **Suivant**.
    
6. Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer. 
    
7. Vérifiez que la **Fédération (port 5061)** est définie sur **activé** dans le générateur de topologies.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>Pour mettre à jour le tronçon suivant de la Fédération du serveur Edge de Skype entreprise Server 2019

1. À partir du générateur de topologie, dans le volet gauche, accédez au nœud **Skype entreprise Server 2019** , puis au nœud **pool** de serveurs Edge. 
    
2. Développez le nœud, cliquez avec le bouton droit sur le serveur Edge listé, puis cliquez sur **Modifier les propriétés**. 
    
3. Dans la page **général** , sous **sélection du tronçon suivant**, sélectionnez dans la liste déroulante le pool Skype entreprise Server 2019.
  
4. Cliquez sur **OK** pour fermer la page Modifier les propriétés. 
    
5. Dans le **Générateur de topologies**, sélectionnez le nœud supérieur **Skype entreprise Server**. 
    
6. Dans le menu **Actions**, cliquez sur **Publier la topologie** et terminez l’Assistant. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>Pour configurer le chemin d’accès sortant du serveur Edge de Skype entreprise Server 2019

1. Dans le volet gauche du générateur de topologie, accédez au nœud **Skype entreprise Server 2019** , puis au pool sous **serveurs frontaux Standard Edition** ou **Pools frontaux Enterprise Edition**.
    
2. Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.
    
3. Dans la section **Associations**, activez la case à cocher **Associer un pool Edge (pour les composants multimédias)**. 
  
4. Dans la zone de liste déroulante, sélectionnez le serveur Edge de Skype entreprise Server 2019.
    
5. Cliquez sur **OK** pour fermer la page **Modifier les propriétés**. 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>Pour activer la Fédération de serveur Edge de Skype entreprise Server 2019

1. À partir du générateur de topologie, dans le volet gauche, accédez au nœud **Skype entreprise Server 2019** , puis au nœud **pool** de serveurs Edge. 
    
2. Développez le nœud, cliquez avec le bouton droit sur le serveur Edge listé, puis cliquez sur **Modifier les propriétés**. 
    
    > [!NOTE]
    > La Fédération ne peut être activée que pour un seul pool de serveurs Edge. Si vous avez plusieurs pools de serveurs Edge, sélectionnez-en un à utiliser comme pool Edge fédérateur. 
  
3. Sur la page **général** , vérifiez que la case à cocher **activer la Fédération pour ce pool Edge (port 5061)** est activée. 
  
4. Cliquez sur **OK** pour fermer la page Modifier les propriétés. 
    
5. Naviguez jusqu’au nœud de site. 
    
6. Cliquez avec le bouton droit sur le site, puis cliquez sur **Modifier les propriétés**.
    
7. Dans le volet gauche, cliquez sur **Itinéraire de fédération**.
    
8. Sous **attribution**de l’itinéraire de Fédération du site, sélectionnez **activer la Fédération SIP**, puis dans la liste, sélectionnez le serveur Edge de Skype entreprise Server 2019 répertorié. 
  
9. Cliquez sur **OK** pour fermer la page **Modifier les propriétés**. 
    
     Pour les déploiements sur plusieurs sites, effectuez cette procédure sur chaque site. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>Pour publier les modifications de configuration du serveur Edge

1. Dans le **Générateur de topologies**, sélectionnez le nœud supérieur **Skype entreprise Server**. 
    
2. Dans le menu **Actions**, sélectionnez **Publier la topologie** et terminez l’Assistant. 
    
3. Attendez que la réplication Active Directory se produise sur tous les pools de serveurs impliqués dans le déploiement.
    
    > [!NOTE]
    > Le message suivant peut s’afficher : **Avertissement : la topologie contient plus d’un serveur Edge fédéré. Cela peut se produire lors de la migration vers une version plus récente du produit. Dans ce cas, un seul serveur Edge est activement utilisé pour la Fédération. Vérifiez que l’enregistrement SRV DNS externe pointe vers le serveur Edge approprié. Si vous souhaitez déployer plusieurs serveurs Edge de Fédération comme étant actifs simultanément (autrement dit, pas un scénario de migration), vérifiez que tous les partenaires fédérés utilisent Skype entreprise Server. Vérifiez que l’enregistrement DNS SRV externe répertorie tous les serveurs Edge de Fédération activés.** Cet avertissement est attendu et peut être ignoré en toute sécurité. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>Pour configurer le serveur Edge de Skype entreprise Server 2019

1. Mettez tous les serveurs Edge Skype entreprise Server 2019 en ligne. 
    
2. Mettez à jour les règles de routage du pare-feu externe ou les paramètres du programme d’équilibrage de la charge matérielle pour envoyer le trafic SIP pour l’accès externe (généralement le port 443) et la Fédération (généralement le port 5061) vers le serveur Edge de Skype entreprise Server 2019, au lieu du serveur Edge hérité.
    
    > [!NOTE]
    > Si vous ne disposez pas d’un programme d’équilibrage de la charge matérielle, vous devez mettre à jour l’enregistrement DNS A de la Fédération pour qu’il soit résolu en nouveau serveur Edge d’accès Skype entreprise Server. Pour effectuer cette opération avec une interruption minimale, réduisez la valeur TLL pour le nom de domaine complet du serveur Edge d’accès externe Skype entreprise Server de sorte que lorsque DNS est mis à jour pour pointer vers le nouveau serveur Edge d’accès Skype entreprise, la Fédération et l’accès à distance seront mis à jour rapidement. 
  
3. Arrêtez le serveur **Edge d’accès Skype entreprise Server** à partir de chaque ordinateur serveur Edge. 
    
4. À partir de chaque ordinateur serveur Edge hérité, ouvrez l’applet **services** à partir des **Outils d’administration**.
    
5. Dans la liste des services, recherchez **serveur Edge d’accès Skype entreprise**.
    
6. Cliquez avec le bouton droit sur le nom du service, puis sélectionnez **Arrêter** pour arrêter le service. 
    
7. Définissez le type de démarrage sur **Désactivé**. 
    
8. Cliquez sur **OK** pour fermer la fenêtre **Propriétés**. 
    

