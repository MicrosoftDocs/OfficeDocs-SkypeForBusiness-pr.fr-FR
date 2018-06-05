---
title: Configuration de CUCM pour l’interopération avec Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: 'Résumé : Configurez CUCM pour fonctionner avec Skype pour Business Server 2015.'
ms.openlocfilehash: 04913508ba0200da4b34e8b1e18c3e57a5fc7141
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19501968"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server-2015"></a>Configuration de CUCM pour l’interopération avec Skype Entreprise Server 2015
 
**Résumé :** Configurer CUCM pour fonctionner avec Skype pour Business Server 2015.
  
> [!CAUTION]
> Cette fonctionnalité est testée avec la version 10.5 de CUCM en configuration de jonctions sur TCP seulement. Vérifiez que l’environnement CUCM remplit ces critères avant de continuer. 
  
Les paramètres décrits ici sont destinées uniquement des exemples de comment CUCM peut être configuré pour fonctionner avec une vis Il est possible d’utiliser d’autres paramètres et/ou de prévoir d’autres utilisations de la fonctionnalité CUCM pour obtenir le même résultat. Aucune recommandation n’est faite en matière de configuration optimale pour un scénario particulier.
  
Il est nécessaire de confirmer ou modifier un certain nombre de paramètres CUCM pour assurer leur interopération avec le VIS. Suivez la procédure suivante pour ne pas oublier des paramètres nécessaires.
  
### <a name="configure-the-cucm"></a>Configurer le CUCM

1. Connectez-vous à CUCM et accédez à Cisco Unified CM Administration -\>appel routage -\>classe de contrôle -\>Partition.
    
2. Sur l’écran Configuration de partition, entrez le nom et la description de la partition, puis cliquez sur **Ajouter nouveau**.
    
3. Accédez à Cisco Unified CM Administration -\>appel routage -\>classe de contrôle -\>espace recherche l’appel.
    
4. Sur l’écran Configuration d’espace de recherche d’appel, entrez le nom de l’espace de recherche d’appel, et dans Partitions sélectionnées, entrez le nom de la partition que vous venez de créer. Cliquez sur **Enregistrer** quand vous avez terminé.
    
5. Accédez à Cisco Unified CM Administration -\>système -\>sécurité -\>profil de sécurité de jonction SIP.
    
6. Sur l’écran Configuration de profil de sécurité des jonctions SIP, configurez les options Informations de profil de sécurité des jonctions SIP comme illustré, puis cliquez sur **Ajouter nouveau**.
    
   |**Paramètre**|**Réglage recommandé**|
   |:-----|:-----|
   |Nom  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |Mode de sécurité d’appareil  <br/> |Non sécurisé  <br/> |
   |Type de transport entrant  <br/> |TCP + UDP  <br/> |
   |Type de transport sortant  <br/> |TCP  <br/> |
   |Port entrant  <br/> |5060  <br/> |
   
7. Accédez à Cisco Unified CM Administration -\>périphérique -\>paramètres du périphérique -\>profil SIP.
    
8. Sur l’écran Configuration de profil SIP, configurez les options Informations de profil SIP comme illustré. 
    
   |**Paramètre**|**Réglage recommandé**|
   |:-----|:-----|
   |Nom  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |Description  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. Dans l’écran de même, faites défiler jusqu'à la section informations de profil SDP. L’option **Modificateur de bande passante au niveau de session SDP pour offre précoce et nouvelle invitation** est configurée sur TIAS et AS par défaut. Changez cette option en indiquant TIAS seulement. Si vous laissez cette option à sa valeur par défaut, Skype pour Business Server ne comprendre les informations du modificateur de bande passante dans le message SIP. TIAS signifie spécifique pour une application indépendante de transport (Transport Independent Application Specific), tandis qu’AS signifie (spécifique pour une application). Il s’agit d’options SIP indiquées dans RFC3890.
    
10. Sur le même écran, faites défiler vers le bas. Sous Configuration spécifique de la jonction du profil SIP, sélectionnez ** tôt prennent en charge pour les appels audio et vidéo ** et affectez-lui l’option **obligatoire (insert MTP si nécessaire)** . Cela permettra à CUCM de configurer un appel SIP sortant avec une offre précoce. Une nouvelle fonctionnalité de CUCM 8.5 et des versions ultérieures est la prise en charge de la configuration des appels sortants avec offre précoce sans point de terminaison multimédia (MTP).
    
11. Vérifiez que, dans la section ping Options SIP, la case est cochée à côté de Activer le ping OPTIONS pour surveiller le statut de destination pour les jonctions avec le type de service Aucun (par défaut).
    
12. Quand vous avez terminé, cliquez sur **Ajouter nouveau**.
    
13. Accédez à Cisco Unified CM Administration -\>périphérique -\>jonction. 
    
14. Configurez le protocole d’appareil sur SIP et appuyez sur **Suivant**.
    
15. Sous Informations d’appareil, configurez le nom et la description du dispositif (probablement SfBVideoInterop_SIPTrunk), puis configurez la liste des groupes de ressources multimédia sur un MRGL qui contient les ressources multimédia appropriées. 
    
16. Faites défiler vers le bas. Le point de terminaison multimédia (MTP) n’est pas obligatoire pour les appels vidéo et, si la case est toujours cochée, désactivez l’option. Activez l’option **Exécuter sur tous les nœuds CM unifiés actifs**. Veuillez noter que vous devez ajouter tous les nœuds CUCM à la Skype pour la configuration du serveur d’entreprise.
    
17. Faites défiler vers le bas. Configurez les options Appels entrants et Paramètres de partie connectée comme illustré.
    
    |**Paramètre**|**Réglage recommandé**|
    |:-----|:-----|
    |Espace de recherche d’appel  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espace de recherche d’appel AAR  <br/> |CSS_SfBVideoInterop  <br/> |
    |CSS de transformation de partie connectée  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. Faites défiler la page vers le bas. Sous la section Destination d’informations SIP de la configuration de jonction SIP, spécifiez le nom de domaine complet du Pool VIS ou l’adresse IP des serveurs individuels de VIS dans le pool (ajout de plusieurs entrées). Dans le port de destination, indiquez le port écouté par le serveur d’interopérabilité vidéo (VIS) pour les connexions à partir de CUCM (la valeur par défaut est 6001). Spécifiez également le profil de sécurité des jonctions SIP et le profil SIP que vous avez créés précédemment, comme indiqué.
    
    |**Paramètre**|**Réglage recommandé**|
    |:-----|:-----|
    |Profil de sécurité des jonctions SIP  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |Réacheminement de l’espace de recherche d’appel  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espace de recherche d’appel avec référence hors de dialogue  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espace de recherche d’appel d’abonnement  <br/> |CSS_SfBVideoInterop  <br/> |
    |Profil SIP  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |Méthode de signalement DTMF  <br/> |RFC 2833  <br/> |
   
19.  Faites défiler vers le bas. Configurez les informations d’enregistrement selon les besoins de votre système. Il convient de laisser la valeur **Aucun**à. 
    
20. Quand vous avez terminé, cliquez sur **Ajouter nouveau**.
    
21. Accédez à Cisco Unified CM Administration -\>appel routage -\>itinéraire/postes-\>modèle d’itinéraire.
    
22. Sur l’écran Configuration de modèle d’itinéraire, entrez les paramètres de définition de modèle indiqués ci-dessous. Faites défiler vers la section Transformations de partie appelée et configurez les masques comme indiqué, puis cliquez sur **Ajouter nouveau** quand vous avez terminé.
    
    |**Paramètre**|**Réglage recommandé**|
    |:-----|:-----|
    |Modèle d’itinéraire  <br/> |7779999  <br/> |
    |Partition d’itinéraire  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Description  <br/> |Partition pour SfBVideoInterop  <br/> |
    |Liste de passerelles/itinéraires  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Masque de transformation de partie appelée  <br/> |+14257779999  <br/> |
   
23. Accédez à Cisco Unified CM Administration -\>appel routage -\>schéma d’acheminement SIP.
    
24. Sur l’écran Configuration de modèle d’itinéraire SIP, configurez les options de définition d’itinéraire comme indiqué, puis cliquez sur **Ajouter nouveau**.
    
    |**Paramètre**|**Réglage recommandé**|
    |:-----|:-----|
    | Utilisation de modèle <br/> |Acheminement de domaine  <br/> |
    |Modèle IPv4  <br/> |contoso.com (laisser vide avec IPv6)  <br/> |
    |Modèle IPv6  <br/> |contoso.com (laisser vide avec IPv4)  <br/> |
    |Description  <br/> |Modèle SIPRoute vers mediarv  <br/> |
    |Partition d’itinéraire  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Liste des jonctions/itinéraires SIP  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Case de modèle de bloc  <br/> |ne pas cocher  <br/> |
   
25. Si vous avez modifié les vitesses de transmission audio ou vidéo par rapport aux valeurs par défaut, vous devrez rétablir les valeurs par défaut. Pour définir la vitesse de transmission pour les appels Audio/vidéo, accédez à Cisco Unified CM Administration -\>système -\>zone informations -\>région. Les valeurs par défaut sont affichées ci-dessous à titre de référence :
    
    |**Paramètre**|**Réglage recommandé**|
    |:-----|:-----|
    |Région  <br/> |Valeur par défaut  <br/> |
    |Liste de préférences codec audio  <br/> |Valeur par défaut du système  <br/> |
    |Vitesse de transmission audio maximale  <br/> |64 Kbit/s (G.722, G.711)  <br/> |
    |Vitesse de transmission de session maximale pour les appels vidéo  <br/> |200 000 Kbits/s  <br/> |
    |Vitesse de transmission de session maximale  <br/> |2 000 000 000 Kbits/s  <br/> |
   
À ce moment, la passerelle vidéo CUCM est configurée pour fonctionner avec le VIS. Il sera nécessaire d’effectuer une configuration correspondante sur chaque VTC que vous souhaitez intégrer.
> [!NOTE]
> Pour améliorer la résistance, vous souhaiterez peut-être configurer cette passerelle CUCM pour fonctionner avec un pool de serveur d’interopérabilité vidéo ou VIS deuxième. Pour obtenir des renseignements complémentaires, veuillez consulter la rubrique [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency).
  
## <a name="see-also"></a>Voir aussi

[Configurer un VTC pour l’interopérabilité avec Skype pour Business Server 2015](configure-a-vtc-for-interoperation.md)