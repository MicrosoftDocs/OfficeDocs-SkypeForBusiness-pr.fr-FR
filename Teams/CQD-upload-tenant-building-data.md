---
title: Télécharger le client et générer des données dans le tableau de bord de qualité des appels (bord)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Découvrez comment télécharger un client et générer des données dans le tableau de bord de qualité des appels (bord).
ms.openlocfilehash: 1ee722e63a8699e1447ffc0c2bc859a6a080d220
ms.sourcegitcommit: bac9aa29074ef32387dc05b3918e87d4c38d195d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/23/2020
ms.locfileid: "49385631"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>Télécharger le client et générer des données dans le tableau de bord de qualité des appels (bord)


Pour tirer le meilleur parti du tableau de bord de qualité des appels (bord), nous vous recommandons de charger votre locataire et de créer des données. Il existe deux types de fichiers de données client, de [construction](#upload-building-data-file) et de [point de terminaison](#endpoint-data-file).

Vous pouvez télécharger un exemple de modèle de données de locataire [ici](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true). Pour obtenir de l’aide sur le mappage de création, voir [créer une carte de construction pour bord](CQD-building-mapping.md).

Dans le tableau de bord des rapports de synthèse de bord, sélectionnez **chargement des données du client** dans le menu **paramètres** de bord (icône d’engrenage en haut de bord). À partir de cet emplacement, les administrateurs peuvent charger les informations de construction et de point de terminaison de votre organisation, telles que le mappage d’adresses IP et d’informations géographiques, le mappage de chaque point d’accès sans fil et son adresse MAC, etc.

1. Ouvrez bord (à partir du centre d’administration teams [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) ), puis sélectionnez l’icône d’engrenage dans le coin supérieur droit et choisissez **Télécharger les données du client** dans la page **rapports de synthèse** .

   ![Capture d’écran de la boîte de dialogue qui s’affiche lorsque les données sont en cours de téléchargement](media/qerguide-image-tenantdataupload.png)
    
2. Si c’est la première fois que vous visitez bord, vous serez invité à télécharger les données de bâtiment. Vous pouvez sélectionner **Télécharger maintenant** pour accéder rapidement à la page **téléchargement de données du client** .

   ![Capture d’écran d’une bannière permettant à un utilisateur de télécharger des données de bâtiment](media/qerguide-image-buildingdatauploadbanner.png)

3. Sur la page **téléchargement de données du client** , sélectionnez **Parcourir** pour choisir un fichier de données.

4. Après avoir sélectionné un fichier de données, spécifiez la **Date de début** et, éventuellement, spécifiez une date de fin.

5. Après avoir sélectionné la **Date de début**, sélectionnez **Télécharger** pour télécharger le fichier sur bord. <br><br>Le fichier est validé avant d’être chargé. En cas d’échec de la validation, un message d’erreur s’affiche et vous demande de corriger le fichier. La figure suivante illustre une erreur qui se produit lorsque le nombre de colonnes dans le fichier de données est incorrect.

   ![Exemple de boîte de dialogue affichant une erreur de chargement de données en bâtiment](media/qerguide-image-buildingdatauploaderror.png)
 
6. S’il n’y a aucune erreur lors de la validation, le chargement du fichier réussit. Vous pouvez ensuite voir le fichier de données chargé dans la table **Mes téléchargements** , qui affiche la liste complète des fichiers téléchargés pour le client actuel en bas de cette page.

> [!NOTE]
> Il faut parfois jusqu’à quatre heures pour terminer le traitement du fichier de construction. <br><br> Si vous avez déjà chargé un fichier de construction et que vous avez besoin d’ajouter des sous-réseaux qui peuvent avoir été manqués ou exclus, modifiez le fichier d’origine en ajoutant le nouveau sous-réseau, supprimez le fichier actif, puis rechargez le fichier que vous venez de modifier. Il ne peut y avoir qu’un seul fichier de données de bâtiment actif dans bord. 


## <a name="upload-building-data-file"></a>Télécharger un fichier de données bâtiment

Le premier type de fichier de données client dans bord est le fichier de données de **bâtiment** . La colonne de sous-réseau repose sur le développement de la colonne Network + plage du réseau, puis sur la colonne de sous-réseau pour le premier sous-réseau de l’enregistrement d’appel ou sur le second sous-réseau. Pour que le format du fichier de données réussisse le contrôle de validation avant le téléchargement, il doit respecter les critères suivants.
  
- Il doit s’agir d’un fichier. TSV (les colonnes sont séparées par une tabulation) ou d’un fichier. csv (les colonnes sont séparées par une virgule).

- Le fichier de données n’inclut pas de ligne d’en-tête de tableau. La première ligne du fichier de données est censée être de véritables données, pas d’étiquettes d’en-tête comme « réseau ».

- Les types de données dans le fichier ne peuvent être que des chaînes, des entiers ou des valeurs booléennes. Pour le type de données Integer, la valeur doit être une valeur numérique. Les valeurs booléennes doivent être égales à 0 ou 1.

- Si une colonne utilise le type de données chaîne, un champ de données peut être vide, mais doit toujours être séparé par une tabulation ou une virgule. Un champ de données vide attribue simplement une valeur de chaîne vide.

- Il doit y avoir 15 colonnes pour chaque ligne, chaque colonne doit avoir le type de données approprié, et les colonnes doivent être dans l’ordre indiqué dans le tableau suivant (délimité par des virgules ou des tabulations) :

  **Créer un format de fichier de données**
  
  | Nom de la colonne        | Type de données | Exemple                   | Aide              |
  |--------------------|-----------|---------------------------|-----------------------|
  | NetworkIP          | String    | 192.168.1.0               | Obligatoire              |
  | Nom réseau        | String    | États-Unis/Seattle/SEATTLE-SEA-1 | Obligatoire<sup>1</sup>  |
  | NetworkRange       | Numéro    | 26/08/03                        | Obligatoire              |
  | BuildingName       | String    | SEATTLE-SEA-1             | Obligatoire<sup>1</sup>  |
  | Type de propriété      | String    | Chez                   | Facultatif              |
  | Type de bâtiment       | String    | Arrêt            | Facultatif              |
  | BuildingOfficeType | String    | Ingénieur               | Facultatif              |
  | Ville               | String    | Seattle                   | Recommandation           |
  | ZipCode            | String    | 98001                     | Recommandation           |
  | Pays            | String    | Nous                        | Recommandation           |
  | État              | String    | WA                        | Recommandation           |
  | Région             | String    | MSUS                      | Recommandation           |
  | Dans l’entreprise<sup>2</sup>         | Bool      | 1             | Obligatoire              |
  | ExpressRoute<sup>3</sup>       | Bool      | 0,4             | Obligatoire              |
  | VPN                | Bool      | 0,4                         | Facultatif              |

  <sup>1</sup> sans être requis par bord, les modèles sont configurés pour afficher les noms de bâtiment et de réseau.

  <sup>2</sup> ce paramètre peut être utilisé pour indiquer si le sous-réseau se trouve ou non dans le réseau d’entreprise. Vous pouvez personnaliser l’utilisation à d’autres fins.

  <sup>3</sup> ce paramètre peut être utilisé pour indiquer si le réseau utilise ou non Azure ExpressRoute. Vous pouvez personnaliser l’utilisation à d’autres fins.  

  **Ligne d’exemple :**

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> La plage réseau peut être utilisée pour représenter un super-réseau (combinaison de plusieurs sous-réseaux avec un seul préfixe de routage). Les nouveaux chargements de construction seront examinés pour toutes les plages qui se chevauchent. Si vous avez déjà téléchargé un fichier de construction, vous devez télécharger le fichier actif et le télécharger à nouveau pour identifier les chevauchements et résoudre le problème avant de le télécharger à nouveau. Tout chevauchement dans les fichiers précédemment téléchargés risque de provoquer des mappages incorrects de sous-réseaux sur les bâtiments dans les rapports. Certaines implémentations de réseau privé virtuel n’indiquent pas exactement les informations de sous-réseau. 
>
> La colonne RPV est facultative et utilise par défaut la valeur 0. Si la valeur de la colonne VPN est définie sur 1, le sous-réseau représenté par cette ligne sera entièrement étendu pour correspondre à toutes les adresses IP au sein du sous-réseau.  N’hésitez pas à utiliser cette fonction et uniquement pour les sous-réseaux VPN dans la mesure où le développement complet de ces sous-réseaux aura un impact négatif sur les requêtes de création de données.


### <a name="supernetting"></a>Le Super-réseautage

Vous pouvez utiliser le Super-réseautage, couramment appelé routage de Inter-Domain de classe (CIDR) au lieu de définir chaque sous-réseau. Un *super-réseau* est une combinaison de plusieurs sous-réseaux partageant un seul préfixe de routage. Au lieu d’ajouter une entrée pour chaque sous-réseau, vous pouvez utiliser l’adresse superréseau. Le Super-réseautage est pris en charge, mais nous ne recommandons pas son utilisation.

Par exemple, le bâtiment marketing de contoso se compose des sous-réseaux suivants :

-   10.1.0.0/24-premier étage
-   10.1.1.0/24-second étage
-   10.1.2.0/24 : troisième étage
-   10.1.3.0/24-quatrième étage

Au lieu d’ajouter une entrée pour chaque sous-réseau, vous pouvez utiliser l’adresse de super-réseau (dans cet exemple, 10.1.0.0/22).

-   Réseau = 10.1.0.0
-   Plage de réseaux = 22

Voici quelques éléments à prendre en compte avant d’implémenter le super-réseau :

-   Le Super-réseautage ne peut être utilisé que dans un mappage de sous-réseau doté d’un masque de 8 bits à 28 bits.

-   Le Super-affichage prend moins de temps, mais il s’agit du coût de la réduction de la richesse de vos données. Imaginons qu’il y a un problème de qualité lié au sous-réseau 10.1.2.0. Si vous avez implémenté le super-réseau, vous ne savez pas où se trouve dans le bâtiment le sous-réseau ou quel type de réseau il est (par exemple, un laboratoire). Si vous avez défini tous les sous-réseaux pour les informations d’emplacement du étage, vous pouvez voir cette distinction.

-   Il est important de veiller à ce que l’adresse du superréseau soit correcte et qu’elle ne soit pas interceptée.

-   Il est relativement courant de Rechercher 192.168.0.0 dans les données. Dans de nombreuses organisations, cela signifie que l’utilisateur est à la maison. Pour d’autres, il s’agit du schéma d’adresse IP d’un bureau satellite. Si votre organisation dispose de bureaux qui utilisent cette configuration, n’incluez pas celle-ci dans votre fichier de bâtiment, car il est difficile de distinguer les réseaux domestiques et internes à l’aide de [sous-réseaux communs](quality-of-experience-review-guide.md#common-subnets). 

> [!IMPORTANT]
> La plage réseau peut être utilisée pour représenter une super-réseau. Les nouveaux téléchargements de fichiers de données de bâtiment seront examinés pour les plages qui se chevauchent. Si vous avez déjà téléchargé un fichier de construction, vous devriez télécharger le fichier actif et le télécharger à nouveau pour identifier les chevauchements et résoudre le problème. Tout chevauchement dans les fichiers précédemment téléchargés peut entraîner des mappages incorrects de sous-réseaux vers les bâtiments dans les rapports.

### <a name="vpn"></a>VPN

Les données de qualité de l’expertise que les clients envoient à Microsoft 365 ou Office 365, à partir duquel les données bord sont sources, incluent un indicateur VPN. BORD le verra comme le premier VPN et les deuxièmes réseaux VPN. Toutefois, cet indicateur repose sur la création d’un rapport de fournisseurs de réseau privé virtuel (VPN) sur Windows, qui s’est inscrit sur une carte d’accès à distance. Les fournisseurs de réseaux VPN n’inscrivent pas correctement les cartes d’accès distant. Pour cette raison, il est possible que vous ne puissiez pas utiliser les filtres de requête VPN intégrés. Utilisez la colonne VPN décrite plus haut pour marquer et identifier précisément les sous-réseaux VPN. Il est également conseillé d’étiqueter vos réseaux VPN pour faciliter l’identification de vos rapports. Vous trouverez ci-dessous deux exemples d’attribution de libellés à vos sous-réseaux VPN :

- Définissez un **nom de réseau** en entrant « VPN » dans ce champ pour les sous-réseaux VPN.

  ![Capture d’écran de rapport QCD montrant un VPN utilisant le nom du réseau](media/qerguide-image-vpnnetworkname.png)

- Définissez un **nom de bâtiment** en entrant « VPN » dans ce champ pour les sous-réseaux VPN.

  ![Capture d’écran de rapport QCD montrant un VPN utilisant le nom de bâtiment](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> Les connexions VPN ont été connues pour identifier le type de connexion réseau comme filaire Lorsque la connexion sous-jacente est sans fil. Lorsque vous examinez la qualité de connexions VPN, vous ne pouvez pas supposer que le type de connexion a été correctement identifié.

## <a name="endpoint-data-file"></a>Fichier de données du point de terminaison

L’autre type de fichier de données client bord est le fichier de données de **point de terminaison** . Les valeurs de colonne sont utilisées dans la première colonne nom du point de terminaison du client ou deuxième nom du point de terminaison du client pour afficher les informations de point de terminaison, de modèle ou de type. Pour que le format du fichier de données réussisse le contrôle de validation avant le téléchargement, il doit respecter les critères suivants.

- Il doit s’agir d’un fichier. TSV (les colonnes sont séparées par une tabulation) ou d’un fichier. csv (les colonnes sont séparées par une virgule).

- Le contenu du fichier de données ne comporte pas d’en-têtes de tableau. La première ligne du fichier de données est censée être une véritable donnée, et non une étiquette d’en-tête telle que « EndpointName ».

- Les sept colonnes utilisent uniquement le type de données chaîne. La longueur maximale autorisée est de 64 caractères.

- Un champ de données peut être vide, mais doit toujours être séparé par une tabulation ou une virgule. Un champ de données vide attribue simplement une valeur de chaîne vide.

- EndpointName doit être unique, sinon le téléchargement échoue. S’il existe une ou deux lignes en double utilisant la même EndpointName, le conflit provoquera une jointure incorrecte.

- EndpointLabel1, EndpointLabel2 et EndpointLabel3 sont des étiquettes personnalisables. Il peut s’agir de chaînes vides ou de valeurs telles que « service informatique de l’ordinateur portable 2018 » ou « indicateur de ressources 5678 ».

- Il doit y avoir sept colonnes pour chaque ligne et les colonnes doivent être dans l’ordre suivant :

  **Ordre des champs :**

  EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Ligne d’exemple :**

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`


## <a name="update-a-building-file"></a>Mettre à jour un fichier de construction

Lors du rassemblement des informations de construction et de sous-réseau, les administrateurs chargent souvent le fichier de construction dans plusieurs itérations, en ajoutant de nouveaux sous-réseaux et leurs informations de bâtiment dès qu’il devient disponible. Lorsque cela se produit, vous devez recharger votre fichier de construction. Ce processus est comme le téléchargement initial comme décrit dans la section précédente, à quelques exceptions près, comme indiqué dans la section suivante.

> [!Important]
> Un seul fichier de construction peut être actif à la fois. Les fichiers de construction multiples ne sont pas cumulés.

## <a name="add-net-new-subnets"></a>Ajouter des sous-réseaux personnels

Il peut arriver que vous deviez ajouter des sous-réseaux de nouveaux réseaux aux bord qui n’étaient pas à l’origine dans la topologie de votre réseau. Pour ajouter de nouveaux sous-réseaux, effectuez l’une des opérations suivantes à partir de la page **téléchargement de données de client** dans bord :

1.  Téléchargez le fichier d’origine, si vous n’avez pas encore de copie à jour.

1.  Supprimez le fichier actif dans bord.

1.  Modifiez le fichier de construction d’origine et indiquez une date de fin au moins un jour avant l’acquisition des sous-réseaux.

1.  Ajoutez les nouveaux sous-réseaux personnels au fichier de construction d’origine.

1.  Téléchargez le fichier de construction qui vient d’être modifié, puis définissez la date de début pour un jour après la fin du fichier de construction précédent.

## <a name="add-missing-subnets"></a>Ajouter des sous-réseaux manquants

Une fois que vous avez chargé les informations de bâtiment pour les réseaux gérés, chaque réseau géré doit avoir une association de bâtiment. Toutefois, ce n’est pas toujours le cas. en règle générale, un petit nombre de sous-réseaux est manqué. Pour trouver ces réseaux manquants, examinez le **rapport de sous-réseau manquant** sur la page **rapports de qualité de l’interface** dans bord. Tous les sous-réseaux avec 10 flux audio ou plus qui ne sont pas définis dans le fichier de données de bâtiment sont marqués comme extérieurs. Assurez-vous qu’il n’y a pas de réseaux gérés dans cette liste. Si des sous-réseaux ne sont pas disponibles, utilisez la procédure suivante pour mettre à jour le fichier de données de construction d’origine et le télécharger à nouveau sur bord.

1. Accédez à la page **Télécharger les données du client** dans bord.

1. Téléchargez le fichier d’origine, si vous n’avez pas encore de copie à jour.

1. Supprimez le fichier actif dans bord.

1. Ajoutez les nouveaux sous-réseaux au fichier d’origine.

1. Téléchargez le fichier de construction. Veillez à définir la date de début sur au moins huit mois avant que bord ne traitera les données historiques.


> [!IMPORTANT]
> Vous devez ajouter votre ID de locataire comme filtre de requête pour le **deuxième ID de client** à ce rapport afin de filtrer le rapport pour afficher uniquement les données client de votre organisation. Dans le cas contraire, le rapport va afficher des sous-réseaux fédérés.

> [!NOTE] 
> Veillez à ajuster le filtre de rapport mois par année au mois en cours. Sélectionnez **modifier**, puis ajustez le filtre de rapport **mois-année** pour enregistrer le nouveau mois par défaut.


## <a name="related-topics"></a>Voir aussi

[Créer une carte de bâtiment pour bord](CQD-building-mapping.md)

[Améliorer et surveiller la qualité des appels pour teams](monitor-call-quality-qos.md)

[Qu’est-ce que bord ?](CQD-what-is-call-quality-dashboard.md)

[Configurer le tableau de bord de qualité des appels (bord)](turning-on-and-using-call-quality-dashboard.md)

[Rapports et données bord](CQD-data-and-reports.md)

[Utiliser bord pour gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md)

[Dimensions et mesures disponibles dans bord](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification des flux dans bord](stream-classification-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser des données de bord](CQD-Power-BI-query-templates.md)
