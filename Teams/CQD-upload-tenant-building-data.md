---
title: Charger des données de locataire et de génération dans le tableau de bord de qualité des appels (CQD)
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Découvrez comment charger le locataire et générer des données dans le tableau de bord de qualité des appels (CQD).
ms.openlocfilehash: d999098a2d920c8709ae1878ac94648451c00f0b
ms.sourcegitcommit: 548978550d58f8657d7035b57b736e9cf9b15984
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/23/2022
ms.locfileid: "69163224"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>Charger des données de locataire et de génération dans le tableau de bord de qualité des appels (CQD)


Pour tirer le meilleur parti du tableau de bord de qualité des appels (CQD), nous vous recommandons de charger votre locataire et de générer des données. Il existe 2 types de fichiers de données de locataire , [Bâtiment](#upload-building-data-file) et [Point de terminaison](#endpoint-data-file).

Vous pouvez télécharger un exemple de modèle de données client [ici](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true). Pour obtenir de l’aide sur la création de mappage, consultez [Créer une carte de bâtiment pour CQD](CQD-building-mapping.md).

Dans le tableau de bord Rapports de synthèse CQD, sélectionnez **Chargement des données** client dans le menu **Paramètres** CQD (icône d’engrenage en haut de CQD). À partir de là, les administrateurs peuvent charger les informations de construction et de point de terminaison de leur organisation, telles que le mappage des adresses IP et des informations géographiques, le mappage de chaque point d’accès sans fil et de son adresse MAC, etc.

1. Ouvrez CQD (à partir du Centre d’administration Teams ou à l’adresse [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)), puis sélectionnez l’icône d’engrenage dans le coin supérieur droit et choisissez **Chargement des données** client dans la page **Rapports de résumé** .

   ![Capture d’écran de la boîte de dialogue qui s’affiche pendant le chargement des données.](media/qerguide-image-tenantdataupload.png)
    
2. Sinon, s’il s’agit de votre première visite au CQD, vous serez invité à charger des données de construction. Vous pouvez sélectionner **Charger maintenant** pour accéder rapidement à la page **Chargement des données du locataire** .

   ![Capture d’écran de la bannière qui avertit un utilisateur de charger des données de création.](media/qerguide-image-buildingdatauploadbanner.png)

3. Dans la page **Chargement des données du locataire** , sélectionnez **Parcourir** pour choisir un fichier de données.

4. Après avoir sélectionné un fichier de données, spécifiez **la date de début** et, éventuellement, spécifiez une date de fin.

5. Après avoir sélectionné **Date de début**, sélectionnez **Charger** pour charger le fichier dans CQD. <br><br>Avant le chargement du fichier, il est validé. Si la validation échoue, un message d’erreur s’affiche pour vous demander de corriger le fichier. La figure suivante montre une erreur qui se produit lorsque le nombre de colonnes dans le fichier de données est incorrect.

   ![Exemple de boîte de dialogue affichant une erreur de chargement de données de construction.](media/qerguide-image-buildingdatauploaderror.png)
 
6. Si aucune erreur ne se produit pendant la validation, le chargement du fichier réussit. Vous pouvez ensuite voir le fichier de données chargé dans la table **Mes chargements** , qui affiche la liste complète de tous les fichiers chargés pour le locataire actuel en bas de cette page.

> [!NOTE]
> Le traitement du fichier de génération peut prendre jusqu’à quatre heures. <br><br> Si vous avez déjà chargé un fichier de création et que vous devez ajouter des sous-réseaux qui ont peut-être été manqués ou exclus, modifiez le fichier d’origine en ajoutant les nouveaux sous-réseaux, supprimez le fichier actuel et chargez à nouveau le fichier nouvellement modifié. Il ne peut y avoir qu’un seul fichier de données de construction actif dans CQD. 


## <a name="upload-building-data-file"></a>Charger le fichier de données de génération

Le premier type de fichier de données client dans CQD est le fichier **de données de génération** . La colonne Sous-réseau est dérivée en développant la colonne Network+NetworkRange, puis en joignant la colonne Sous-réseau à la colonne Premier sous-réseau ou Deuxième sous-réseau de l’enregistrement d’appel pour afficher les informations sur le bâtiment, la ville, le pays ou la région. Le format du fichier de données que vous chargez doit répondre aux critères suivants pour réussir la vérification de validation avant le chargement :
  
- Le fichier doit être un fichier .tsv (les colonnes sont séparées par une tabulation) ou un fichier .csv (les colonnes sont séparées par une virgule).

- Le fichier de données n’inclut pas de ligne d’en-tête de tableau. La première ligne du fichier de données est censée être des données réelles, et non des étiquettes d’en-tête comme « Réseau ».

- Les types de données dans le fichier peuvent uniquement être String, Integer ou Boolean. Pour le type de données Integer, la valeur doit être une valeur numérique. Les valeurs booléennes doivent être 0 ou 1.

- Si une colonne utilise le type de données String, un champ de données peut être vide, mais doit toujours être séparé par un onglet ou une virgule. Un champ de données vide affecte simplement une valeur string vide.

- Il existe une limite de lignes étendue de 1 000 000 par fichier de données client.

- Il doit y avoir 15 colonnes pour chaque ligne, chaque colonne doit avoir le type de données approprié et les colonnes doivent être dans l’ordre indiqué dans le tableau suivant (délimitées par des virgules ou des tabulations) :

  **Création d’un format de fichier de données**
  
  | Nom de la colonne        | Type de données | Exemple                   | Aide              |
  |--------------------|-----------|---------------------------|-----------------------|
  | NetworkIP          | String    | 192.168.1.0               | Obligatoire              |
  | NetworkName        | String    | États-Unis/Seattle/SEATTLE-SEA-1 | Obligatoire<sup>1</sup>  |
  | NetworkRange       | Numéro    | 26                        | Obligatoire              |
  | BuildingName       | String    | SEATTLE-SEA-1             | Obligatoire<sup>1</sup>  |
  | PropriétéType      | String    | Contoso                   | Facultatif<sup>4</sup>  |
  | BuildingType       | String    | Arrêt informatique            | Facultatif<sup>4</sup>  |
  | BuildingOfficeType | String    | Ingénierie               | Facultatif<sup>4</sup>  |
  | Ville               | String    | Seattle                   | Recommandation           |
  | ZipCode            | String    | 98001                     | Recommandation           |
  | Pays            | String    | Nous                        | Recommandation           |
  | État              | String    | WA                        | Recommandation           |
  | Région             | String    | MSUS                      | Recommandation           |
  | InsideCorp<sup>2</sup>         | Bool      | 1             | Obligatoire              |
  | ExpressRoute<sup>3</sup>       | Bool      | 0             | Obligatoire              |
  | VPN                | Bool      | 0                         | Facultatif              |

  <sup>1</sup> Bien qu’ils ne soient pas requis par CQD, les modèles sont configurés pour afficher le nom du bâtiment et du réseau.

  <sup>2</sup> Ce paramètre peut être utilisé pour indiquer si le sous-réseau se trouve ou non à l’intérieur du réseau d’entreprise. Vous pouvez personnaliser l’utilisation à d’autres fins.

  <sup>3</sup> Ce paramètre peut être utilisé pour déterminer si le réseau utilise Ou non Azure ExpressRoute. Vous pouvez personnaliser l’utilisation à d’autres fins.  
  
  <sup>4</sup> Bien que ces colonnes facultatives soient nommées pour suggérer les valeurs avec lesquelles vous souhaitez peut-être les remplir, vous pouvez personnaliser l’utilisation à d’autres fins. par exemple : Priorité réseau - `Tier 1, Tier 2, Tier 3` 

  **Exemple de ligne :**

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> La plage réseau peut être utilisée pour représenter un surnet (combinaison de plusieurs sous-réseaux avec un préfixe de routage unique). Tous les chargements de nouveaux bâtiments seront vérifiés pour détecter les plages qui se chevauchent. Si vous avez déjà chargé un fichier de génération, vous devez télécharger le fichier actuel et le charger à nouveau pour identifier les chevauchements et résoudre le problème avant de le charger à nouveau. Tout chevauchement dans les fichiers précédemment chargés peut entraîner des mappages incorrects des sous-réseaux aux bâtiments dans les rapports. Certaines implémentations VPN ne signalent pas avec précision les informations de sous-réseau. 
>
> La colonne VPN est facultative et la valeur par défaut est 0. Si la valeur de la colonne VPN est définie sur 1, le sous-réseau représenté par cette ligne est entièrement développé pour correspondre à toutes les adresses IP du sous-réseau. Utilisez cela avec parcimonie et uniquement pour les sous-réseaux VPN, car le développement complet de ces sous-réseaux aura un impact négatif sur les temps de requête pour les requêtes impliquant la création de données. Si l’extension du sous-réseau entraîne le dépassement de la limite de lignes d’extension de 1 000 000, le fichier de génération n’est pas accepté.


### <a name="supernetting"></a>Supernetting

Vous pouvez utiliser le supernetting, communément appelé CIDR (Classless Inter-Domain Routing), au lieu de définir chaque sous-réseau. Un *surnet* est une combinaison de plusieurs sous-réseaux qui partagent un préfixe de routage unique. Au lieu d’ajouter une entrée pour chaque sous-réseau, vous pouvez utiliser l’adresse superposée. Le surnetting est pris en charge, mais nous vous déconseillons de l’utiliser.

Par exemple, le bâtiment marketing de Contoso est constitué des sous-réseaux ci-dessous :

-   10.1.0.0/24 — premier étage
-   10.1.1.0/24 — deuxième étage
-   10.1.2.0/24 — troisième étage
-   10.1.3.0/24 — quatrième étage

Au lieu d’ajouter une entrée pour chaque sous-réseau, vous pouvez utiliser l’adresse superposée( dans cet exemple, 10.1.0.0/22).

-   Réseau = 10.1.0.0
-   Plage réseau = 22

Voici quelques points à prendre en compte avant d’implémenter le surnetting :

-   Le surnetting peut uniquement être utilisé dans un mappage de sous-réseau avec un masque 8 bits à 28 bits.

-   Le supernetting prend moins de temps à l’avance, mais cela se fait au détriment de la richesse de vos données. Supposons qu’il existe un problème de qualité impliquant le sous-réseau 10.1.2.0. Si vous avez implémenté le supernetting, vous ne savez pas où se trouve le sous-réseau dans le bâtiment ni quel type de réseau il s’agit (par exemple, un labo). Si vous aviez défini tous les sous-réseaux pour un bâtiment et chargé les informations d’emplacement de l’étage, vous serez en mesure de voir cette distinction.

-   Il est important de s’assurer que l’adresse en supernette est correcte et qu’elle n’intercepte pas les sous-réseaux indésirables.

-   Il est assez courant de trouver 192.168.0.0 dans les données. Pour de nombreuses organisations, cela indique que l’utilisateur est chez lui. Pour d’autres, il s’agit du schéma d’adresse IP d’un bureau satellite. Si votre organisation a des bureaux qui utilisent cette configuration, ne l’incluez pas dans votre fichier de création, car il est difficile de faire la distinction entre les réseaux domestiques et internes à l’aide [de sous-réseaux communs](quality-of-experience-review-guide.md#common-subnets). 

> [!IMPORTANT]
> La plage réseau peut être utilisée pour représenter un surnet. Tous les nouveaux chargements de fichiers de données de construction seront vérifiés pour détecter les plages qui se chevauchent. Si vous avez déjà chargé un fichier de création, vous devez télécharger le fichier actuel et le charger à nouveau pour identifier les chevauchements et résoudre le problème. Tout chevauchement dans les fichiers précédemment chargés peut entraîner des mappages incorrects des sous-réseaux aux bâtiments dans les rapports.

### <a name="vpn"></a>VPN

Les données de qualité d’expérience (QoE) envoyées par les clients à Microsoft 365 ou Office 365, à partir de laquelle proviennent les données CQD, incluent un indicateur VPN. CQD considère cela comme les dimensions premier VPN et deuxième VPN. Toutefois, cet indicateur s’appuie sur les rapports des fournisseurs VPN à Windows indiquant que la carte réseau VPN inscrite est une carte d’accès à distance. Tous les fournisseurs VPN n’inscrivent pas correctement les adaptateurs d’accès à distance. Pour cette raison, vous ne pourrez peut-être pas utiliser les filtres de requête VPN intégrés. Utilisez la colonne VPN décrite ci-dessus pour marquer et identifier avec précision les sous-réseaux VPN. Il est également recommandé d’étiqueter vos réseaux VPN pour faciliter l’identification dans vos rapports. Voici deux exemples d’étiqueter vos sous-réseaux VPN :

- Définissez un **nom réseau** en entrant « VPN » dans ce champ pour les sous-réseaux VPN.

  ![Capture d’écran du rapport QCD montrant un VPN utilisant un nom réseau.](media/qerguide-image-vpnnetworkname.png)

- Définissez un **nom de bâtiment** en entrant « VPN » dans ce champ pour les sous-réseaux VPN.

  ![Capture d’écran du rapport QCD montrant le VPN utilisant le nom du bâtiment.](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> On sait que les connexions VPN identifient mal le type de connexion réseau comme étant câblée lorsque la connexion sous-jacente est sans fil. Lorsque vous examinez la qualité des connexions VPN, vous ne pouvez pas supposer que le type de connexion a été identifié avec précision.

## <a name="endpoint-data-file"></a>Fichier de données de point de terminaison

L’autre type de fichier de données client CQD est le fichier de données **de point de terminaison** . Les valeurs de colonne sont utilisées dans la colonne Nom du premier point de terminaison client ou Nom du deuxième point de terminaison client de l’enregistrement d’appel pour afficher les informations Nom, Modèle ou Type du point de terminaison. Le format du fichier de données que vous chargez doit répondre aux critères suivants pour réussir la vérification de validation avant le chargement :

- Le fichier doit être un fichier .tsv (les colonnes sont séparées par une tabulation) ou un fichier .csv (les colonnes sont séparées par une virgule).

- Le contenu du fichier de données n’inclut pas d’en-têtes de tableau. La première ligne du fichier de données est censée être des données réelles, et non une étiquette d’en-tête comme « EndpointName ».

- Les sept colonnes utilisent uniquement le type de données String. La longueur maximale autorisée est de 64 caractères.

- Les entrées respectent la casse ; EndpointName **ABC123** sera traité comme unique à partir de EndpointName **abc123**.

- Un champ de données peut être vide, mais doit toujours être séparé par un onglet ou une virgule. Un champ de données vide affecte simplement une valeur string vide.

- EndpointName doit être unique, sinon le chargement échoue. S’il existe une ou deux lignes en double qui utilisent le même EndpointName, le conflit entraîne une jointure incorrecte.

- EndpointLabel1, EndpointLabel2 et EndpointLabel3 sont des étiquettes personnalisables. Il peut s’agir de chaînes ou de valeurs vides telles que « It Department designated 2018 Laptop » ou « Asset Tag 5678 ».

- Il doit y avoir sept colonnes pour chaque ligne et les colonnes doivent être dans l’ordre suivant :

  **Ordre des champs :**

  EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Exemple de ligne :**

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a>Mettre à jour un fichier de génération

Lors de la collecte d’informations sur le bâtiment et le sous-réseau, les administrateurs chargent souvent le fichier de construction en plusieurs itérations au fil du temps, en ajoutant de nouveaux sous-réseaux et leurs informations de création à mesure qu’ils deviennent disponibles. Dans ce cas, vous devez charger à nouveau votre fichier de génération. Ce processus est semblable au chargement initial décrit dans la section précédente, à quelques exceptions près comme indiqué dans la section suivante.

> [!Important]
> Un seul fichier de génération peut être actif à la fois. Les fichiers de génération multiples ne sont pas cumulatifs.

## <a name="add-net-new-subnets"></a>Ajouter de nouveaux sous-réseaux nets

Il arrive que vous deviez ajouter de nouveaux sous-réseaux nets à CQD qui ne faisaient pas partie à l’origine de votre topologie de réseau. Pour ajouter de nouveaux sous-réseaux nets, procédez comme suit à partir de la page **Chargement de données** client dans CQD :

1.  Téléchargez le fichier d’origine, si vous n’avez pas encore de copie à jour.

1.  Supprimez le fichier actuel dans CQD.

1.  Modifiez le fichier de construction d’origine et indiquez une date de fin qui se produit au moins un jour avant l’acquisition des nouveaux sous-réseaux nets.

1.  Ajoutez les nouveaux sous-réseaux nets au fichier de construction d’origine.

1.  Chargez le fichier de construction nouvellement modifié et définissez la date de début pour un jour après la fin du fichier de génération précédent.

## <a name="add-missing-subnets"></a>Ajouter des sous-réseaux manquants

Une fois que vous avez chargé les informations de génération pour les réseaux managés, chaque réseau managé doit avoir une association de bâtiments. Toutefois, ce ne sera pas toujours le cas; en règle générale, quelques sous-réseaux sont manquants. Pour trouver ces réseaux manquants, consultez le **rapport de sous-réseau manquant** dans la page **Rapports sur la qualité de l’expérience** dans CQD. Cela présente tous les sous-réseaux avec au moins 10 flux audio qui ne sont pas définis dans le fichier de données de création et qui sont marqués comme étant à l’extérieur. Vérifiez qu’il n’y a aucun réseau managé dans cette liste. Si des sous-réseaux sont manquants, utilisez la procédure suivante pour mettre à jour le fichier de données de construction d’origine et le charger à nouveau dans CQD.

1. Accédez à la page **Chargement des données** client dans CQD.

1. Téléchargez le fichier d’origine, si vous n’avez pas encore de copie à jour.

1. Supprimez le fichier actuel dans CQD.

1. Ajoutez les nouveaux sous-réseaux au fichier d’origine.

1. Chargez le fichier de génération. Veillez à définir la date de début sur au moins huit mois avant afin que CQD traite les données historiques.


> [!IMPORTANT]
> Vous devez ajouter votre ID de locataire en tant que filtre de requête pour **l’ID de deuxième locataire** à ce rapport afin de filtrer le rapport afin d’afficher uniquement les données de locataire de votre organisation. Sinon, le rapport affiche les sous-réseaux fédérés.

> [!NOTE] 
> Veillez à ajuster le filtre de rapport Mois année sur le mois en cours. Sélectionnez **Modifier**, puis ajustez le filtre **de rapport Mois année** pour enregistrer le nouveau mois par défaut.


## <a name="related-topics"></a>Rubriques connexes

[Créer une carte de construction pour CQD](CQD-building-mapping.md)

[Améliorer et surveiller la qualité des appels pour Teams](monitor-call-quality-qos.md)

[Qu’est-ce que le TBQA ?](CQD-what-is-call-quality-dashboard.md)

[Configurer le tableau de bord de qualité des appels (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Données et rapports du TBQA](CQD-data-and-reports.md)

[Utiliser le TBQA pour gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md)

[Dimensions et mesures disponibles dans le TBQA](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification de flux de données dans le TBQA](stream-classification-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser les données TBQA](CQD-Power-BI-query-templates.md)
