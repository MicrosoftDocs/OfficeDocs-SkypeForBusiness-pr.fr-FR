---
title: Configurer CUCM pour l’interopération avec Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: 'Résumé : Configurez CUCM pour qu’il fonctionne avec Skype Entreprise Server.'
ms.openlocfilehash: 2e5e2cfc207fd9c4e52f7cd4da553dc756fddb4c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863091"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>Configurer CUCM pour l’interopération avec Skype Entreprise Server
 
**Résumé :** Configurez CUCM pour qu’il fonctionne avec Skype Entreprise Server.
  
> [!CAUTION]
> Cette fonctionnalité est testée avec Cisco Unified Communications Manager (CallManager, ou CUCM) version 10.5 à l’aide de l’installation de Trunks sur TCP uniquement. Vérifiez que l’environnement CUCM répond à ces critères avant de poursuivre. 
  
Les paramètres décrits ici ne sont destinés qu’à des exemples de la façon dont CUCM peut être configuré pour fonctionner avec un VIS. D’autres paramètres et/ou utilisations d’autres fonctionnalités CUCM peuvent également être utilisés pour obtenir le même résultat. Aucune recommandation n’est implicite quant à la configuration optimale pour un scénario particulier.
  
Un certain nombre de paramètres CUCM doivent être confirmés ou modifiés pour l’interopérabilité avec le VIS. Suivez les procédures ci-dessous afin d’éviter l’absence de paramètres requis.
  
### <a name="configure-the-cucm"></a>Configurer le CUCM

1. Connectez-vous au CUCM et accédez à Administration CM unifiée Cisco - Routage des \> appels - Classe de contrôle - \> \> Partition.
    
2. Dans l’écran Configuration de la partition, entrez le nom et la description de la partition, puis cliquez sur **Ajouter nouveau**.
    
3. Accédez à Administration CM unifiée Cisco - \> Routage des appels - \> Classe de contrôle - Espace de recherche \> d’appel.
    
4. Dans l’écran Configuration de l’espace de recherche d’appel, entrez le nom de l’espace de recherche appelant, puis dans Partitions sélectionnées, entrez le nom de la partition que vous avez créée. Cliquez **sur Enregistrer** lorsque vous avez terminé.
    
5. Accédez à Administration CM unifiée Cisco – \> Système - Sécurité - Profil de sécurité de la ligne \> \> SIP.
    
6. Dans l’écran Configuration du profil de sécurité de la trunk SIP, définissez les options d’informations de profil de sécurité de la trunk SIP comme indiqué, puis cliquez sur **Ajouter nouveau**.
    
   |**Paramètre**|**Valeur recommandée**|
   |:-----|:-----|
   |Nom  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |Mode sécurité de l’appareil  <br/> |Non sécurisé  <br/> |
   |Type de transport entrant  <br/> |TCP + UDP  <br/> |
   |Type de transport sortant  <br/> |TCP  <br/> |
   |Port entrant  <br/> |5060  <br/> |
   
7. Accédez à Administration CM unifiée Cisco - \> Appareil - \> Paramètres- Profil \> SIP.
    
8. Dans l’écran Configuration du profil SIP, définissez les options Informations de profil SIP comme indiqué. 
    
   |**Paramètre**|**Valeur recommandée**|
   |:-----|:-----|
   |Nom  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |Description  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. Sur le même écran, faites défiler vers le bas jusqu’à la section Informations de profil SDP. L’option Modificateur de bande passante au niveau de la session SDP pour les offres et les **invitations anticipées** est définie par défaut sur TIAS et AS. Modifiez cette option en TIAS uniquement. Si vous laissez cette option à sa valeur par défaut, Skype Entreprise Server ne comprend pas les informations de modificateur de bande passante dans le message SIP. TIAS signifie « Transport Independent Application Specific » tandis que « AS » signifie « Application Specific ». Voici les options SIP spécifiées dans RFC3890.
    
10. Sur le même écran, faites défiler vers le bas. Sous configuration spécifique de la trunk  du profil SIP, sélectionnez Prise en charge de l’offre anticipée pour les appels vocal et vidéo et définissez-la sur l’option Obligatoire **(insérer MTP si nécessaire).** Cela permettra à CUCM de configurer un appel SIP sortant avec l’offre anticipée. Une nouvelle fonctionnalité de CUCM 8.5 et au-delà est qu’elle prend en charge la configuration des appels sortants avec l’offre anticipée sans nécessiter de point de terminaison multimédia (MTP).
    
11. Vérifiez que dans la section Ping options SIP, la case est cochée en face de « Activer OPTIONS Ping pour surveiller l’état de destination des tronçons avec le type de service « Aucun (par défaut) ».
    
12. Lorsque vous avez terminé, cliquez sur **Ajouter nouveau**.
    
13. Accédez à Administration CM unifiée Cisco - \> Appareil - \> Trunk. 
    
14. Définissez le protocole de périphérique sur SIP et appuyez sur **Suivant**.
    
15. Sous Informations sur l’appareil, définissez le nom et la description de l’appareil (probablement à SfBVideoInterop_SIPTrunk), et définissez la liste des groupes de ressources multimédias sur un MRGL qui contient les ressources multimédias appropriées. 
    
16. Faites défiler vers le bas. Le point de terminaison multimédia (MTP) n’est pas requis pour les appels vidéo, s’il n’est pas déjà décoché, décochez-le. Cochez l’option **Exécuter sur tous les nodes CM unifiés actifs.** Veuillez noter que vous devez ajouter tous les nodes CUCM à la configuration Skype Entreprise Server’ordinateur.
    
17. Faites défiler vers le bas. Définissez les options d’appels entrants et de Paramètres comme indiqué.
    
    |**Paramètre**|**Valeur recommandée**|
    |:-----|:-----|
    |Appel de l’espace de recherche  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espace de recherche d’appel AAR  <br/> |CSS_SfBVideoInterop  <br/> |
    |CSS de transformation de partie connectée  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. Faites défiler vers le bas. Sous la section Destination des informations SIP de la configuration de tronçon SIP, spécifiez le FQDN du pool VIS ou l’adresse IP des serveurs VIS individuels du pool (ajout de plusieurs entrées). Dans le port de destination, spécifiez le port d’écoute du VIS pour les connexions à partir de CUCM (la valeur par défaut est 6001). Spécifiez également le profil de sécurité de la trunk SIP et le profil SIP que vous avez créés précédemment, comme illustré.
    
    |**Paramètre**|**Valeur recommandée**|
    |:-----|:-----|
    |Profil de sécurité des trunks SIP  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |Réroutage de l’espace de recherche d’appel  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espace de recherche d’appel de référence hors boîte de dialogue  <br/> |CSS_SfBVideoInterop  <br/> |
    |S’abonner à l’espace de recherche d’appel  <br/> |CSS_SfBVideoInterop  <br/> |
    |Profil SIP  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |DTMF Signaling Method  <br/> |RFC 2833  <br/> |
   
19.  Faites défiler vers le bas. Définissez les informations d’enregistrement selon le cas pour votre système. Il est correct de le laisser sur **Aucun**. 
    
20. Lorsque vous avez terminé, cliquez sur **Ajouter nouveau**.
    
21. Accédez à Administration cm unifiée Cisco - \> Routage des appels- \> Itinéraire/Itinéraire de \> recherche- Modèle d’itinéraire.
    
22. Dans l’écran Configuration du modèle d’itinéraire, entrez les paramètres de définition de modèle indiqués ci-dessous. Faites défiler vers le bas jusqu’à la section Transformations de l’appelé et définissez le masque comme indiqué, puis cliquez sur Ajouter **nouveau** lorsque vous avez terminé.
    
    |**Paramètre**|**Valeur recommandée**|
    |:-----|:-----|
    |Modèle d’itinéraire  <br/> |7779999  <br/> |
    |Partition de l’itinéraire  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Description  <br/> |Partition pour SfBVideoInterop  <br/> |
    |Liste des passerelles/itinéraires  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Masque de transformation de partie appelée  <br/> |+14257779999  <br/> |
   
23. Accédez à Administration CM unifiée Cisco - Routage des \> appels - Modèle \> d’itinéraire SIP.
    
24. Dans l’écran Configuration du modèle d’itinéraire SIP, définissez les options de définition de modèle comme indiqué, puis cliquez sur **Ajouter nouveau**.
    
    |**Paramètre**|**Valeur recommandée**|
    |:-----|:-----|
    | Utilisation des modèles <br/> |Routage de domaine  <br/> |
    |Modèle IPv4  <br/> |contoso.com (laisser vide si vous utilisez IPv6)  <br/> |
    |Modèle IPv6  <br/> |contoso.com (laisser vide si vous utilisez IPv4)  <br/> |
    |Description  <br/> |Modèle SIPRoute vers mediarv  <br/> |
    |Partition de l’itinéraire  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Liste des itinéraires/liaisons SIP  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Case à cocher Motif de bloc  <br/> |laisser désactivé  <br/> |
   
25. Si vous avez modifié les taux de bits audio ou vidéo par rapport aux paramètres par défaut, vous devez les renvoyer aux valeurs par défaut. Pour définir la vitesse de bits pour les appels audio/vidéo, accédez à Administration cm unifiée Cisco - Système - Informations \> sur la région - \> \> Région. Les valeurs par défaut sont indiquées ci-dessous pour référence :
    
    |**Paramètre**|**Valeur recommandée**|
    |:-----|:-----|
    |Région  <br/> |Par défaut  <br/> |
    |Liste des préférences de codec audio  <br/> |Système par défaut  <br/> |
    |Vitesse de bits audio maximale  <br/> |64 Kbits/s (G.722, G.711)  <br/> |
    |Vitesse maximale de session pour les appels vidéo  <br/> |200000 Kbits/s  <br/> |
    |Vitesse de bits maximale de session  <br/> |2000000000 Kbits/s  <br/> |
   
À ce stade, la passerelle vidéo CUCM est configurée pour fonctionner avec le VIS. La configuration correspondante doit être effectuée sur chaque VTC que vous souhaitez intégrer.
> [!NOTE]
> Pour améliorer la résilience, vous pouvez configurer cette passerelle CUCM de manière à ce qu’elle fonctionne avec un deuxième serveur d’interconnexion vidéo ou un pool VIS. Pour plus [d’informations, voir mécanismes](../../plan-your-deployment/video-interop-server.md#resiliency) de résilience.
  
## <a name="see-also"></a>Voir aussi

[Configurer un VTC pour l’interopération avec Skype Entreprise Server](configure-a-vtc-for-interoperation.md)
