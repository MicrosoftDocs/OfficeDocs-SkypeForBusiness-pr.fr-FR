---
title: Exemple de rassemblement des exigences de contrôle d’admission des appels dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
description: Fournit un exemple détaillé de la planification du contrôle d’admission des appels dans la voix Skype entreprise Server entreprise, notamment la collecte d’informations sur les sites, les régions et la bande passante de votre réseau.
ms.openlocfilehash: 73a1a75f8619877d2c9228f910aa747aee36a8e0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276879"
---
# <a name="example-gathering-requirements-for-call-admission-control-in-skype-for-business-server"></a>Exemple: rassemblement des exigences de contrôle d’admission des appels dans Skype entreprise Server

Fournit un exemple détaillé de la planification du contrôle d’admission des appels dans la voix Skype entreprise Server entreprise, notamment la collecte d’informations sur les sites, les régions et la bande passante de votre réseau.

Cet exemple indique comment planifier et implémenter le contrôle d’admission des appels (CAC). Globalement, il s’agit des activités suivantes :

1. Identifiez l’ensemble de vos concentrateurs réseau et dorsales principales (connues aussi sous le nom de régions réseau).

2. Identifiez le site central Skype entreprise Server qui gère le CAC pour chaque région du réseau.

3. Identifiez et définissez les sites réseau connectés à chaque région réseau.

4. Pour chaque site réseau pour lequel la connexion au réseau étendu (WAN) est soumise à une bande passante, décrivez la capacité de bande passante utilisée par la connexion WAN et les limites de bande passante pour le trafic multimédia de Skype entreprise Server, le cas échéant. Il n’est pas nécessaire d’inclure les sites dont la bande passante de connexion de réseau étendu n’est pas limitée.

5. Associez chaque sous-réseau de votre réseau à un site réseau.

6. Mappez les liaisons entre régions réseau. Pour chaque lien, décrivez la capacité de la bande passante et les limites que l’administrateur réseau a placées sur le trafic multimédia de Skype entreprise Server.

7. Définissez un itinéraire entre chaque paire de régions réseau.

## <a name="gather-the-required-information"></a>Rassembler les informations requises

Pour préparer le contrôle d’admission des appels, rassemblez les informations présentées dans les étapes suivantes :

1. Identifiez vos régions réseau. Une région réseau représente une dorsale principale ou un concentrateur réseau. 

    Une dorsale principale ou un concentrateur réseau fait partie de l’infrastructure réseau informatique qui interconnecte différents éléments du réseau, fournissant ainsi un chemin pour l’échange des informations entre différents réseaux locaux (LAN) ou sous-réseaux. Une dorsale principale peut lier divers réseaux d’un petit emplacement à une zone géographique étendue. La capacité de la dorsale principale est généralement plus grande que celle des réseaux qui s’y connectent.

    Notre exemple de topologie comporte trois régions réseau : Amérique du Nord, EMEA et APAC. Une région réseau contient une collection de sites réseau. Définissez les régions réseau de votre entreprise avec l’administrateur réseau.

2. Identifiez le site central associé de chaque région du réseau. Un site central comporte au moins un serveur frontal et est le déploiement de Skype entreprise Server qui gère le CAC pour l’ensemble du trafic multimédia transmis par le biais de la connexion WAN de la région du réseau.

   **Exemple de réseau d’entreprise divisé en trois régions réseau**

     ![Exemple de topologie réseau avec 3 régions réseau](../../media/Plan_CS_VoiceCAC_example3networkregions.jpg)

    > [!NOTE]
    > Un réseau MPLS (Multiprotocol Label Switching) devrait être représenté en tant que région réseau dans laquelle un emplacement géographique est associé à un site réseau correspondant. Pour plus d’informations, reportez-vous à la rubrique [composants et topologies pour le contrôle d’admission des appels dans Skype entreprise](components-and-topologies.md). 

    Dans la topologie réseau de l’exemple précédent, il existe trois régions réseau, chacune avec un site central Skype entreprise Server qui gère CAC. Le site central approprié pour une région de réseau est choisi par le voisinage géographique. Dans la mesure où le trafic multimédia sera le plus lourd dans les régions du réseau, la propriété de l’élément géographique voisin le rend autonome et restera opérationnel même si d’autres sites centraux deviennent indisponibles. 

    Dans cet exemple, un déploiement Skype entreprise appelé Chicago est le site central pour la région Amérique du Nord.

    Tous les utilisateurs Skype entreprise en Amérique du Nord sont hébergés sur des serveurs dans le déploiement de Chicago. Le tableau ci-dessous répertorie les sites centraux pour les trois régions réseau.

    **Régions réseau et leur site central associé**

    |**Région réseau**|**Site central**|
    |:-----|:-----|
    |Amérique du Nord  <br/> |Chicago  <br/> |
    |EMEA  <br/> |Londres  <br/> |
    |APAC  <br/> |Pékin  <br/> |

    > [!NOTE]
    > En fonction de votre topologie de Skype entreprise Server, le même site central peut être attribué à plusieurs zones du réseau. 

3. Pour chaque région réseau, identifiez tous les sites réseau (bureaux ou emplacements) dont les connexions au réseau étendu ne sont pas soumises à une limite de bande passante. Comme ces sites disposent de liaisons réseau dont la bande passante n’est pas limitée, il n’est pas nécessaire de leur appliquer des stratégies de bande passante CAC.

    Dans l’exemple présenté dans le tableau suivant, trois sites réseau disposent de liaisons réseau dont la bande passante n’est pas limitée : New York, Chicago et Détroit.

   **Sites réseau non limités par la bande passante de la connexion de réseau étendu**


   | **Site réseau** | **Région réseau**   |
   |:-----------------|:---------------------|
   | New York  <br/>  | Amérique du Nord  <br/> |
   | Chicago  <br/>   | Amérique du Nord  <br/> |
   | Detroit  <br/>   | Amérique du Nord  <br/> |


4. Pour chaque région réseau, identifiez tous les sites réseau se connectant à la région réseau via des liaisons de réseau étendu dont la bande passante est limitée.

    Pour garantir la qualité de l’audio et de la vidéo, nous recommandons de surveiller les réseaux de réseau étendu des sites dont la bande passante est limitée et d’imposer des stratégies de bande passante CAC limitant le flux multimédia (vocal ou vidéo) à partir de et vers la région réseau.

    Dans l’exemple présenté dans le tableau suivant, trois sites réseaux sont limités par la bande passante du réseau étendu : Portland, Reno et Albuquerque.

   **Sites réseau limités par la bande passante de la connexion de réseau étendu**

   |**Site réseau**|**Région réseau**|
   |:-----|:-----|
   |Albuquerque  <br/> |Amérique du Nord  <br/> |
   |Reno  <br/> |Amérique du Nord  <br/> |
   |Portland  <br/> |Amérique du Nord  <br/> |

   **Région réseau CAC Amérique du Nord et trois sites réseau non limités par la bande passante (Chicago, New York et Détroit) et trois sites réseau limités par la bande passante de la liaison de réseau étendu (Portland, Reno et Albuquerque)**

     ![Exemples de sites réseau limités par la bande passante de la connexion WAN](../../media/Plan_CS_VoiceCAC_comparisonof6regionsandconstraints.jpg)

5. Pour chaque liaison de réseau étendu dont la bande passante est limitée, déterminez les points suivants :

   - Limite de bande passante globale à appliquer à toutes les sessions audio simultanées. Si une nouvelle session audio entraîne la dépassement de cette limite, Skype entreprise Server n’autorise pas le démarrage de la session.

   - Limite de bande passante à appliquer à chaque session audio individuelle. La bande passante CAC par défaut est de 175 Kbits/s, mais elle est modifiable par l’administrateur.

   - Limite de bande passante globale à appliquer à toutes les sessions vidéo simultanées. Si une nouvelle session vidéo ne sera pas dépassée, Skype entreprise Server n’autorise pas le démarrage de la session.

   - Limite de bande passante à appliquer à chaque session vidéo individuelle. La bande passante CAC par défaut est de 700 Kbits/s, mais elle est modifiable par l’administrateur.

     **Sites réseau et informations de restriction de bande passante de réseau étendu (bande passante en Kbits/s)**


     | **Site réseau**   | **Région réseau**   | **Limite BP**      | **Limite audio**   | **Limite de session audio** | **Limite vidéo**   | **Limite de session vidéo** |
     |:-------------------|:---------------------|:------------------|:------------------|:------------------------|:------------------|:------------------------|
     | Albuquerque  <br/> | Amérique du Nord  <br/> | 5 000  <br/>      | 2 000  <br/>      | 175  <br/>              | 1 400  <br/>      | 700  <br/>              |
     | Reno  <br/>        | Amérique du Nord  <br/> | 10 000  <br/>     | 4 000  <br/>      | 175  <br/>              | 2 800  <br/>      | 700  <br/>              |
     | Portland  <br/>    | Amérique du Nord  <br/> | 5 000  <br/>      | 4 000  <br/>      | 175  <br/>              | 2 800  <br/>      | 700  <br/>              |
     | New York  <br/>    | Amérique du Nord  <br/> | (aucune limite)  <br/> | (aucune limite)  <br/> | (aucune limite)  <br/>       | (aucune limite)  <br/> | (aucune limite)  <br/>       |
     | Chicago  <br/>     | Amérique du Nord  <br/> | (aucune limite)  <br/> | (aucune limite)  <br/> | (aucune limite)  <br/>       | (aucune limite)  <br/> | (aucune limite)  <br/>       |
     | Detroit  <br/>     | Amérique du Nord  <br/> | (aucune limite)  <br/> | (aucune limite)  <br/> | (aucune limite)  <br/>       | (aucune limite)  <br/> | (aucune limite)  <br/>       |


6. Pour chaque sous-réseau du réseau, indiquez son site réseau associé.

    > [!IMPORTANT]
    > Chaque sous-réseau doit être associé à un site réseau, même si le site réseau n’est pas soumis à une limite de bande passante. Cela est dû au fait que le contrôle d’admission des appels utilise les informations relatives aux sous-réseaux pour déterminer sur quel site réseau un point de terminaison doit se situer. Lorsque les emplacements de chaque partie de la session sont déterminés, le contrôle d’admission des appels peut déterminer si la bande passante est suffisante pour établir l’appel. Lorsqu’une session est établie sur une liaison dont la bande passante n’est pas limitée, une alerte est générée. 

    > [!IMPORTANT]
    > Si vous déployez des serveurs Edge A/V, les adresses IP publiques de chaque serveur Edge doivent être associées au site réseau sur lequel le serveur Edge est déployé. Vous devez ajouter chaque adresse IP publique du serveur Edge A/V à vos paramètres de configuration réseau en tant que sous-réseau avec un masque de sous réseau de 32. Par exemple, si vous déployez des serveurs Edge A/V à Chicago, pour chaque adresse IP externe de ces serveurs, créez un sous-réseau avec un masque de sous-réseau de 32 et associez le site réseau Chicago à ces sous-réseaux. Pour plus d’informations sur les adresses IP publiques, reportez-vous à [Plan network requirements for Skype for Business](../../plan-your-deployment/network-requirements/network-requirements.md). 

    Une alerte d’indicateur d’intégrité clé est générée, indiquant une liste d’adresses IP figurant dans votre réseau, mais non associées à un sous-réseau ou figurant dans un sous-réseau non associé à un site réseau. L’alerte n’est générée qu’une seule fois par période de 8 heures. Les informations d’alerte pertinentes et un exemple sont présentés ci-dessous :

    **Source** : Service de stratégie de bande passante (principal) CS 

    **Numéro d’événement** : 36034

    **Niveau** : 2

    **Description**: les sous-réseaux pour les adresses IP suivantes \<: une liste d'\> adresses IP n’est pas configurée ou les sous-réseaux ne sont pas associés à un site réseau. 

    **Cause** : les sous-réseaux pour les adresses IP correspondantes sont absents des paramètres de configuration du réseau ou les sous-réseaux ne sont pas associés à un site réseau. 

    **Résolution** : ajoutez les sous-réseaux pour les adresses IP correspondantes aux paramètres de configuration du réseau et associez chaque sous-réseau à un site réseau.

    Par exemple, si la liste d’adresses IP qui s’affiche dans l’alerte indique 10.121.248.226 et 10.121.249.20, soit ces adresses IP ne sont pas associées à un sous-réseau, soit le sous-réseau auquel elles sont associées n’appartient pas au site réseau. Si 10.121.248.0/24 et 10.121.249.0/24 sont les sous-réseaux associés à ces adresses, vous pouvez résoudre le problème comme suit :

    a. Vérifiez que l’adresse IP 10.121.248.226 est associée au sous-réseau 10.121.248.0/24 et l’adresse IP 10.121.249.20 au sous-réseau 10.121.249.0/24.

    b. Vérifiez que les sous-réseaux 10.121.248.0/24 et 10.121.249.0/24 sont chacun associés à un site réseau.

   **Sites réseau et sous-réseaux associés (bande passante en Kbits/s)**


   | **Site réseau**   | **Région réseau**   | **Limite BP**      | **Limite audio**   | **Limite de session audio** | **Limite vidéo**   | **Limite de session vidéo** | **Sous-réseaux**                                                            |
   |:-------------------|:---------------------|:------------------|:------------------|:------------------------|:------------------|:------------------------|:-----------------------------------------------------------------------|
   | Albuquerque  <br/> | Amérique du Nord  <br/> | 5 000  <br/>      | 2 000  <br/>      | 175  <br/>              | 1 400  <br/>      | 700  <br/>              | 172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24  <br/> |
   | Reno  <br/>        | Amérique du Nord  <br/> | 10 000  <br/>     | 4 000  <br/>      | 175  <br/>              | 2 800  <br/>      | 700  <br/>              | 157.57.210.0/23, 172.28.151.128/25  <br/>                              |
   | Portland  <br/>    | Amérique du Nord  <br/> | 5 000  <br/>      | 4 000  <br/>      | 175  <br/>              | 2 800  <br/>      | 700  <br/>              | 172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23  <br/>                  |
   | New York  <br/>    | Amérique du Nord  <br/> | (aucune limite)  <br/> | (aucune limite)  <br/> | (aucune limite)  <br/>       | (aucune limite)  <br/> | (aucune limite)  <br/>       | 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24  <br/> |
   | Chicago  <br/>     | Amérique du Nord  <br/> | (aucune limite)  <br/> | (aucune limite)  <br/> | (aucune limite)  <br/>       | (aucune limite)  <br/> | (aucune limite)  <br/>       | 157.57.211.0/23, 172.28.152.128/25  <br/>                              |
   | Detroit  <br/>     | Amérique du Nord  <br/> | (aucune limite)  <br/> | (aucune limite)  <br/> | (aucune limite)  <br/>       | (aucune limite)  <br/> | (aucune limite)  <br/>       | 172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23  <br/>                  |


7. Dans le contrôle d’admission des appels de Skype entreprise Server, les connexions entre les régions réseau sont appelées liaisons de région. Pour chaque lien de région, déterminez ce qui suit, tout comme vous l’avez fait pour les sites réseau :

   - Limite de bande passante globale à appliquer à toutes les sessions audio simultanées. Si une nouvelle session audio entraîne la dépassement de cette limite, Skype entreprise Server n’autorise pas le démarrage de la session.

   - Limite de bande passante à appliquer à chaque session audio individuelle. La bande passante CAC par défaut est de 175 Kbits/s, mais elle est modifiable par l’administrateur.

   - Limite de bande passante globale à appliquer à toutes les sessions vidéo simultanées. Si une nouvelle session vidéo ne sera pas dépassée, Skype entreprise Server n’autorise pas le démarrage de la session.

   - Limite de bande passante à appliquer à chaque session vidéo individuelle. La bande passante CAC par défaut est de 700 Kbits/s, mais elle est modifiable par l’administrateur.

   **Liens de région réseau et limites de bande passante associées**

     ![Exemple de limitations entre 3 régions](../../media/Plan_CS_VoiceCAC_limitsbetween3regions.jpg)

   **Information de bande passante du lien de région (bande passante en Kbits/s)**


   | **Nom de la liaison réseau**  | **Première région**     | **Seconde région** | **Limite BP**  | **Limite audio** | **Limite de session audio** | **Limite vidéo** | **Limite de session vidéo** |
   |:----------------------|:---------------------|:------------------|:--------------|:----------------|:------------------------|:----------------|:------------------------|
   | NA-EMEA-LINK  <br/>   | Amérique du Nord  <br/> | EMEA  <br/>       | 50 000  <br/> | 20 000  <br/>   | 175  <br/>              | 14 000  <br/>   | 700  <br/>              |
   | EMEA-APAC-LINK  <br/> | EMEA  <br/>          | APAC  <br/>       | 25 000  <br/> | 10 000  <br/>   | 175  <br/>              | 7 000  <br/>    | 700  <br/>              |


8. Définissez un itinéraire entre chaque paire de régions réseau.

    > [!NOTE]
    > Deux liaisons sont nécessaires à l’itinéraire entre les régions Amérique du Nord et APAC, car aucun lien de région ne les relie directement. 

   **Itinéraires de région**


   | **Nom de l’itinéraire**  | **Première région**     | **Seconde région** | **Liens de région**                    |
   |:-----------------------|:---------------------|:------------------|:------------------------------------|
   | NA-EMEA-ROUTE  <br/>   | Amérique du Nord  <br/> | EMEA  <br/>       | NA-EMEA-LINK  <br/>                 |
   | EMEA-APAC-ROUTE  <br/> | EMEA  <br/>          | APAC  <br/>       | EMEA-APAC-LINK  <br/>               |
   | NA-APAC-ROUTE  <br/>   | Amérique du Nord  <br/> | APAC  <br/>       | NA-EMEA-LINK, EMEA-APAC-LINK  <br/> |


9. Pour chaque paire de sites réseau directement connectée à une seule liaison (appelée liaison intersite), déterminez ce qui suit :

     - Limite de bande passante globale à appliquer à toutes les sessions audio simultanées. Si une nouvelle session audio entraîne la dépassement de cette limite, Skype entreprise Server n’autorise pas le démarrage de la session.

     - Limite de bande passante à appliquer à chaque session audio individuelle. La bande passante CAC par défaut est de 175 Kbits/s, mais elle est modifiable par l’administrateur.

     - Limite de bande passante globale à appliquer à toutes les sessions vidéo simultanées. Si une nouvelle session vidéo ne sera pas dépassée, Skype entreprise Server n’autorise pas le démarrage de la session.

     - Limite de bande passante à appliquer à chaque session vidéo individuelle. La bande passante CAC par défaut est de 700 Kbits/s, mais elle est modifiable par l’administrateur.

   **Région réseau CAC Amérique du Nord avec les capacités et les limites de bande passante de la liaison intersite entre Reno et Albuquerque**

     ![Exemple de sites réseau limités par la bande passante de la connexion WAN](../../media/Plan_CS_VoiceCAC_limitsforNAdirectlinksRenoAlbuq.jpg)

   **Information de bande passante d’une liaison intersite entre deux sites réseau (bande passante en Kbits/s)**

   |**Nom de la liaison intersite**|**Premier site**|**Second site**|**Limite BP**|**Limite audio**|**Limite de session audio**|**Limite vidéo**|**Limite de session vidéo**|
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |Reno-Albu-Intersite-Link  <br/> |Reno  <br/> |Albuquerque  <br/> |20 000  <br/> |12 000  <br/> |175  <br/> |5 000  <br/> |700  <br/> |

### <a name="next-steps"></a>Étapes suivantes

Après avoir recueilli les informations requises, vous pouvez effectuer le déploiement CAC à l’aide de Skype entreprise Server Management Shell ou du panneau de configuration Skype entreprise Server.

> [!NOTE]
> Même si vous pouvez effectuer la plupart des tâches de configuration réseau en utilisant le panneau de configuration Skype entreprise Server, pour créer des sous-réseaux et des liaisons intersites, vous devez utiliser Skype entreprise Server Management Shell. Pour plus d’informations, reportez-vous aux rubriques [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps) et [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps). 


