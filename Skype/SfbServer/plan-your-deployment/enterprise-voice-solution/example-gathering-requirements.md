---
title: Exemple de collecte des besoins pour un appel de contrôle d’admission dans Skype pour Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
description: Fournit un exemple détaillé de la planification d’appel de contrôle d’admission dans Skype pour de Voix Entreprise Server Business, y compris la collecte d’informations sur les sites, les régions et la bande passante de votre réseau.
ms.openlocfilehash: 1ff42aa9b26eb614ad8f09c15526236b10386da3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="example-gathering-requirements-for-call-admission-control-in-skype-for-business-server-2015"></a>Exemple : collecte des données de configuration requise pour le contrôle d’admission des appels dans Skype Entreprise Server 2015
 
Fournit un exemple détaillé de la planification d’appel de contrôle d’admission dans Skype pour de Voix Entreprise Server Business, y compris la collecte d’informations sur les sites, les régions et la bande passante de votre réseau.
  
Cet exemple indique comment planifier et implémenter le contrôle d’admission des appels (CAC). Globalement, il s’agit des activités suivantes :
  
1. Identifiez tous les concentrateurs de réseau et aux dorsales (connues en tant que zones de réseau).
    
2. Identifier le Skype pour site central Business Server qui gérera le CAC pour chaque zone du réseau.
    
3. Identifier et définir les sites de réseau qui sont connectés à chaque zone du réseau.
    
4. Pour chaque site de réseau dont la connexion au réseau étendu est soumis à des contraintes de bande passante, décrire la capacité de la bande passante de la connexion WAN et les limites de la bande passante qui, à l’administrateur réseau a défini pour Skype pour le trafic multimédia de serveur d’entreprise, le cas échéant. Il n’est pas nécessaire d’inclure les sites dont la bande passante de connexion de réseau étendu n’est pas limitée.
    
5. Associez chaque sous-réseau de votre réseau à un site réseau.
    
6. Mappez les liaisons entre régions réseau. Pour chaque liaison, décrire sa capacité de bande passante et les limites de l’administrateur réseau a placé sur Skype pour le trafic de media Business Server.
    
7. Définissez un itinéraire entre chaque paire de régions réseau.
    
## <a name="gather-the-required-information"></a>Rassembler les informations requises

Pour préparer le contrôle d’admission des appels, rassemblez les informations présentées dans les étapes suivantes :
  
1. Identifiez vos régions réseau. Une région réseau représente une dorsale principale ou un concentrateur réseau. 
    
    Une dorsale principale ou un concentrateur réseau fait partie de l’infrastructure réseau informatique qui interconnecte différents éléments du réseau, fournissant ainsi un chemin pour l’échange des informations entre différents réseaux locaux (LAN) ou sous-réseaux. Une dorsale principale peut lier divers réseaux d’un petit emplacement à une zone géographique étendue. La capacité de la dorsale principale est généralement plus grande que celle des réseaux qui s’y connectent.
    
    Notre exemple de topologie comporte trois régions réseau : Amérique du Nord, EMEA et APAC. Une région réseau contient une collection de sites réseau. Définissez les régions réseau de votre entreprise avec l’administrateur réseau.
    
2. Identifiez le site central du chaque zone réseau associé. Un site central contient au moins un serveur frontal et le Skype pour le déploiement de serveur d’entreprise gérant CAC pour tout le trafic multimédia qui passe via une connexion WAN de la région réseau.
    
   **Un exemple de réseau d’entreprise divisée en trois zones de réseau**

     ![Exemple de topologie réseau avec 3 régions réseau](../../media/Plan_CS_VoiceCAC_example3networkregions.jpg)
  
    > [!NOTE]
    > Un réseau MPLS (Multiprotocol Label Switching) devrait être représenté en tant que région réseau dans laquelle un emplacement géographique est associé à un site réseau correspondant. Pour plus d’informations, consultez la rubrique «[composants et les topologies pour appellent le contrôle d’admission dans Skype pour entreprise 2015](components-and-topologies.md)» dans la documentation de planification. 
  
    Dans la topologie de réseau exemple précédent, il y a trois zones de réseau, chacun avec un Skype pour site Business Server central qui gère la CAC. Le site central approprié pour une zone réseau est choisi par la proximité géographique. Dans la mesure où le trafic multimédia sera plus lourd dans des régions de réseau, la propriété par proximité géographique rend autonomes et continue à être fonctionnelle même si d’autres sites centraux ne sont plus disponibles. 
    
    Dans cet exemple, un Skype pour le déploiement d’entreprise nommé Chicago est le site central pour la région de l’Amérique du Nord.
    
    Tous les Skype pour les utilisateurs professionnels en Amérique du Nord sont hébergés sur des serveurs dans le déploiement de Chicago. Le tableau ci-dessous répertorie les sites centraux pour les trois régions réseau.
    
    **Zones de réseaux et de leurs Sites Central associés**

    |**Région de réseau**|**Site Central**|
    |:-----|:-----|
    |Amérique du Nord  <br/> |Chicago  <br/> |
    |EMEA  <br/> |Londres  <br/> |
    |APAC  <br/> |Pékin  <br/> |
   
    > [!NOTE]
    > Selon votre Skype pour la topologie du serveur de l’entreprise, le même site central peut avoir plusieurs régions du réseau. 
  
3. Pour chaque région réseau, identifiez tous les sites réseau (bureaux ou emplacements) dont les connexions au réseau étendu ne sont pas soumises à une limite de bande passante. Comme ces sites disposent de liaisons réseau dont la bande passante n’est pas limitée, il n’est pas nécessaire de leur appliquer des stratégies de bande passante CAC.
    
    Dans l’exemple présenté dans le tableau suivant, trois sites réseau disposent de liaisons réseau dont la bande passante n’est pas limitée : New York, Chicago et Détroit.
    
   **Sites de réseau ne pas limitées par la bande passante WAN**

   |**Site de réseau**|**Région de réseau**|
   |:-----|:-----|
   |New York  <br/> |Amérique du Nord  <br/> |
   |Chicago  <br/> |Amérique du Nord  <br/> |
   |Detroit  <br/> |Amérique du Nord  <br/> |
   
4. Pour chaque région réseau, identifiez tous les sites réseau se connectant à la région réseau via des liaisons de réseau étendu dont la bande passante est limitée.
    
    Pour garantir la qualité de l’audio et de la vidéo, nous recommandons de surveiller les réseaux de réseau étendu des sites dont la bande passante est limitée et d’imposer des stratégies de bande passante CAC limitant le flux multimédia (vocal ou vidéo) à partir de et vers la région réseau.
    
    Dans l’exemple présenté dans le tableau suivant, trois sites réseaux sont limités par la bande passante du réseau étendu : Portland, Reno et Albuquerque.
    
   **Sites de réseau limités par la bande passante WAN**

   |**Site de réseau**|**Région de réseau**|
   |:-----|:-----|
   |Albuquerque  <br/> |Amérique du Nord  <br/> |
   |Reno  <br/> |Amérique du Nord  <br/> |
   |Portland  <br/> |Amérique du Nord  <br/> |
   
   **Réseau CAC région en Amérique du Nord avec trois sites de réseau qui ne sont pas limités par la bande passante (, New York, Chicago et Detroit) et trois sites de réseau qui sont limités par la bande passante WAN (Portland Reno et Albuquerque)**

     ![Exemples de sites réseau limités par la bande passante de la connexion WAN](../../media/Plan_CS_VoiceCAC_comparisonof6regionsandconstraints.jpg)
  
5. Pour chaque liaison de réseau étendu dont la bande passante est limitée, déterminez les points suivants :
    
  - Limite de bande passante globale à appliquer à toutes les sessions audio simultanées. Si une nouvelle session audio entraîne le dépassement de cette limite, Skype pour Business Server ne permet pas de démarrer la session.
    
  - Limite de bande passante à appliquer à chaque session audio individuelle. La bande passante CAC par défaut est de 175 Kbits/s, mais elle est modifiable par l’administrateur.
    
  - Limite de bande passante globale à appliquer à toutes les sessions vidéo simultanées. Si une nouvelle session vidéo entraîne le dépassement de cette limite, Skype pour Business Server ne permet pas de démarrer la session.
    
  - Limite de bande passante à appliquer à chaque session vidéo individuelle. La bande passante CAC par défaut est de 700 Kbits/s, mais elle est modifiable par l’administrateur.
    
    **Sites de réseau avec les informations de contrainte de la bande passante WAN (bande passante en Kbits/s)**

    |**Site de réseau**|**Région de réseau**|**Limite de bande passante**|**Limite de l’audio**|**Limite de Session audio**|**Limite de vidéo**|**Limite de Session vidéo**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |Albuquerque  <br/> |Amérique du Nord  <br/> |5 000  <br/> |2 000  <br/> |175  <br/> |1 400  <br/> |700  <br/> |
    |Reno  <br/> |Amérique du Nord  <br/> |10 000  <br/> |4 000  <br/> |175  <br/> |2 800  <br/> |700  <br/> |
    |Portland  <br/> |Amérique du Nord  <br/> |5 000  <br/> |4 000  <br/> |175  <br/> |2 800  <br/> |700  <br/> |
    |New York  <br/> |Amérique du Nord  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |
    |Chicago  <br/> |Amérique du Nord  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |
    |Detroit  <br/> |Amérique du Nord  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |
   
6. Pour chaque sous-réseau du réseau, indiquez son site réseau associé.
    
    > [!IMPORTANT]
    > Chaque sous-réseau doit être associé à un site réseau, même si le site réseau n’est pas soumis à une limite de bande passante. Cela est dû au fait que le contrôle d’admission des appels utilise les informations relatives aux sous-réseaux pour déterminer sur quel site réseau un point de terminaison doit se situer. Lorsque les emplacements de chaque partie de la session sont déterminés, le contrôle d’admission des appels peut déterminer si la bande passante est suffisante pour établir l’appel. Lorsqu’une session est établie sur une liaison dont la bande passante n’est pas limitée, une alerte est générée. 
  
    > [!IMPORTANT]
    > Si vous déployez des serveurs Edge A/V, les adresses IP publiques de chaque serveur Edge doivent être associées au site réseau sur lequel le serveur Edge est déployé. Vous devez ajouter chaque adresse IP publique du serveur Edge A/V à vos paramètres de configuration réseau en tant que sous-réseau avec un masque de sous réseau de 32. Par exemple, si vous déployez des serveurs Edge A/V à Chicago, pour chaque adresse IP externe de ces serveurs, créez un sous-réseau avec un masque de sous-réseau de 32 et associez le site réseau Chicago à ces sous-réseaux. Pour plus d’informations sur les adresses IP publiques, reportez-vous à la section [planifier la configuration réseau requise pour Skype pour entreprise 2015](../../plan-your-deployment/network-requirements/network-requirements.md). 
  
    Une alerte d’indicateur d’intégrité clé est générée, indiquant une liste d’adresses IP figurant dans votre réseau, mais non associées à un sous-réseau ou figurant dans un sous-réseau non associé à un site réseau. L’alerte n’est générée qu’une seule fois par période de 8 heures. Les informations d’alerte pertinentes et un exemple sont présentés ci-dessous :
    
    **Source** : Service de stratégie de bande passante (principal) CS 
    
    **Numéro d’événement** : 36034
    
    **Niveau** : 2
    
    **Description**: les sous-réseaux pour l’adresse IP suivante : \<liste d’adresses IP\> sont soit pas configurés ou les sous-réseaux ne sont pas associées à un site de réseau. 
    
    **Cause** : les sous-réseaux pour les adresses IP correspondantes sont absents des paramètres de configuration du réseau ou les sous-réseaux ne sont pas associés à un site réseau. 
    
    **Résolution** : ajoutez les sous-réseaux pour les adresses IP correspondantes aux paramètres de configuration du réseau et associez chaque sous-réseau à un site réseau.
    
    Par exemple, si la liste d’adresses IP qui s’affiche dans l’alerte indique 10.121.248.226 et 10.121.249.20, soit ces adresses IP ne sont pas associées à un sous-réseau, soit le sous-réseau auquel elles sont associées n’appartient pas au site réseau. Si 10.121.248.0/24 et 10.121.249.0/24 sont les sous-réseaux associés à ces adresses, vous pouvez résoudre le problème comme suit :
    
    a. Vérifiez que l’adresse IP 10.121.248.226 est associée au sous-réseau 10.121.248.0/24 et l’adresse IP 10.121.249.20 au sous-réseau 10.121.249.0/24.
    
    b. Vérifiez que les sous-réseaux 10.121.248.0/24 et 10.121.249.0/24 sont chacun associés à un site réseau.
    
   **Réseau de Sites et les sous-réseaux associés (bande passante en Kbits/s)**

   |**Site de réseau**|**Région de réseau**|**Limite de bande passante**|**Limite de l’audio**|**Limite de Session audio**|**Limite de vidéo**|**Limite de Session vidéo**|**Sous-réseaux**|
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |Albuquerque  <br/> |Amérique du Nord  <br/> |5 000  <br/> |2 000  <br/> |175  <br/> |1 400  <br/> |700  <br/> |172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24  <br/> |
   |Reno  <br/> |Amérique du Nord  <br/> |10 000  <br/> |4 000  <br/> |175  <br/> |2 800  <br/> |700  <br/> |157.57.210.0/23, 172.28.151.128/25  <br/> |
   |Portland  <br/> |Amérique du Nord  <br/> |5 000  <br/> |4 000  <br/> |175  <br/> |2 800  <br/> |700  <br/> |172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23  <br/> |
   |New York  <br/> |Amérique du Nord  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24  <br/> |
   |Chicago  <br/> |Amérique du Nord  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |157.57.211.0/23, 172.28.152.128/25  <br/> |
   |Detroit  <br/> |Amérique du Nord  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |(aucune limite)  <br/> |172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23  <br/> |
   
7. Dans Skype Business Server appel de contrôle d’admission, les connexions entre les régions du réseau sont appelées liens de région. Pour chaque lien de région, déterminez ce qui suit, tout comme vous l’avez fait pour les sites réseau :
    
   - Limite de bande passante globale à appliquer à toutes les sessions audio simultanées. Si une nouvelle session audio entraîne le dépassement de cette limite, Skype pour Business Server ne permet pas de démarrer la session.
    
   - Limite de bande passante à appliquer à chaque session audio individuelle. La bande passante CAC par défaut est de 175 Kbits/s, mais elle est modifiable par l’administrateur.
    
   - Limite de bande passante globale à appliquer à toutes les sessions vidéo simultanées. Si une nouvelle session vidéo entraîne le dépassement de cette limite, Skype pour Business Server ne permet pas de démarrer la session.
    
   - Limite de bande passante à appliquer à chaque session vidéo individuelle. La bande passante CAC par défaut est de 700 Kbits/s, mais elle est modifiable par l’administrateur.
    
   **Liens de région de réseau avec des limites de la bande passante associée**

     ![Exemple de limitations entre 3 régions](../../media/Plan_CS_VoiceCAC_limitsbetween3regions.jpg)
  
   **Informations de la bande passante de lien région (bande passante en Kbits/s)**

   |**Nom du lien de la région**|**Première région**|**Deuxième région**|**Limite de bande passante**|**Limite de l’audio**|**Limite de Session audio**|**Limite de vidéo**|**Limite de Session vidéo**|
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |NA-EMEA-LINK  <br/> |Amérique du Nord  <br/> |EMEA  <br/> |50 000  <br/> |20 000  <br/> |175  <br/> |14 000  <br/> |700  <br/> |
   |EMEA-APAC-LINK  <br/> |EMEA  <br/> |APAC  <br/> |25 000  <br/> |10 000  <br/> |175  <br/> |7 000  <br/> |700  <br/> |
   
8. Définissez un itinéraire entre chaque paire de régions réseau.
    
    > [!NOTE]
    > Deux liaisons sont nécessaires à l’itinéraire entre les régions Amérique du Nord et APAC, car aucun lien de région ne les relie directement. 
  
   **Itinéraires de zone**

   |**Zone Nom de l’itinéraire**|**Première région**|**Deuxième région**|**Liens de la région**|
   |:-----|:-----|:-----|:-----|
   |NA-EMEA-ROUTE  <br/> |Amérique du Nord  <br/> |EMEA  <br/> |NA-EMEA-LINK  <br/> |
   |EMEA-APAC-ROUTE  <br/> |EMEA  <br/> |APAC  <br/> |EMEA-APAC-LINK  <br/> |
   |NA-APAC-ROUTE  <br/> |Amérique du Nord  <br/> |APAC  <br/> |NA-EMEA-LINK, EMEA-APAC-LINK  <br/> |
   
9. Pour chaque paire de sites de réseau qui sont directement connectés par une liaison unique (appelée un lien entre les sites), déterminez les éléments suivants :
    
     - Limite de bande passante globale à appliquer à toutes les sessions audio simultanées. Si une nouvelle session audio entraîne le dépassement de cette limite, Skype pour Business Server ne permet pas de démarrer la session.
    
     - Limite de bande passante à appliquer à chaque session audio individuelle. La bande passante CAC par défaut est de 175 Kbits/s, mais elle est modifiable par l’administrateur.
    
     - Limite de bande passante globale à appliquer à toutes les sessions vidéo simultanées. Si une nouvelle session vidéo entraîne le dépassement de cette limite, Skype pour Business Server ne permet pas de démarrer la session.
    
     - Limite de bande passante à appliquer à chaque session vidéo individuelle. La bande passante CAC par défaut est de 700 Kbits/s, mais elle est modifiable par l’administrateur.
    
   **Région de réseau CAC indiquant les capacités de bande passante et les limites de la bande passante de la liaison entre les sites entre Reno et Albuquerque en Amérique du Nord**

     ![Exemple de sites réseau limités par la bande passante de la connexion WAN](../../media/Plan_CS_VoiceCAC_limitsforNAdirectlinksRenoAlbuq.jpg)
  
   **Informations de la bande passante d’un lien entre les sites entre deux Sites réseau (bande passante en Kbits/s)**

   |**Nom du lien de Site entre**|**Premier Site**|**Deuxième Site**|**Limite de bande passante**|**Limite de l’audio**|**Limite de Session audio**|**Limite de vidéo**|**Limite de Session vidéo**|
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |Reno-Albu-Intersite-Link  <br/> |Reno  <br/> |Albuquerque  <br/> |20 000  <br/> |12 000  <br/> |175  <br/> |5 000  <br/> |700  <br/> |
   
### <a name="next-steps"></a>Étapes suivantes

Après avoir recueilli les informations requises, vous pouvez effectuer le déploiement CAC soit en utilisant le Skype pour Business Server Management Shell ou Skype pour le panneau de configuration de Business Server.
  
> [!NOTE]
> Bien que vous pouvez effectuer la plupart des tâches de configuration de réseau à l’aide de Skype pour le panneau de configuration de Business Server, pour créer des sous-réseaux et liens intersites, vous devez utiliser Skype pour Business Server Management Shell. Pour plus d’informations, consultez [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps) et [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps). 
  

