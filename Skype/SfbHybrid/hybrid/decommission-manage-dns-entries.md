---
title: Gérer les entrées DNS lors de la désaffectation de votre environnement local
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instructions sur la gestion des entrées DNS lors de la désaffectation de votre environnement Skype Entreprise local.
ms.openlocfilehash: c21a736c19ecec41ddc0458931675ca8ede34ed2
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671880"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>Mettre à jour les entrées DNS pour permettre à votre organisation d’être toutes Teams uniquement

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Les organisations qui avaient précédemment des déploiements locaux de Skype Entreprise Server ou Lync Server peuvent toujours avoir des entrées DNS qui pointent vers un déploiement Skype Entreprise local. Ces enregistrements sont requis si votre organisation inclut des utilisateurs locaux Skype Entreprise. Toutefois, une fois que votre organisation n’a plus d’utilisateurs locaux Skype Entreprise ou Lync Server, ces enregistrements d’origine ne sont plus requis par le déploiement local et **ces entrées DNS doivent être mises à jour pour pointer vers Microsoft 365 (ou dans certains cas supprimés) dans** le cadre de votre migration de l’environnement local vers Teams Uniquement. *Microsoft ne peut pas mettre à jour ces enregistrements DNS en votre nom.*

Lorsque vous tentez d’accorder TeamsOnly à l’ensemble du locataire, Teams vérifiera DNS pour déterminer si l’un de ces enregistrements DNS répertoriés ci-dessous existe dans chacun de vos domaines vérifiés Microsoft 365 dans votre organisation. Si des enregistrements sont trouvés et qu’ils pointent vers autre chose que Microsoft 365, la tentative de modification du mode de coexistence de locataire en Mode TeamsOnly échoue par conception. Cela empêche les organisations hybrides avec des utilisateurs locaux d’appliquer par erreur le mode TeamsOnly au locataire, car cela interromprait la fédération pour tous les utilisateurs locaux Skype Entreprise de l’organisation (qu’ils utilisent Teams ou Skype Entreprise).

## <a name="how-to-identify-stale-dns-records"></a>Comment identifier les enregistrements DNS obsolètes

Pour identifier les enregistrements DNS qui empêchent votre organisation de devenir tous Teams uniquement, vous pouvez utiliser le centre d’administration Teams pour remplacer le mode de coexistence par TeamsOnly. Accédez à **Teams** >  **Teams paramètres de mise à niveau**. Tous les enregistrements DNS qui empêchent l’organisation de devenir Teams Uniquement sont inclus dans le message d’erreur.  Si aucun enregistrement DNS n’est trouvé, le mode de coexistence de votre organisation sera remplacé par TeamsOnly.

Vous pouvez également utiliser Teams PowerShell pour faire la même chose, comme indiqué ci-dessous :

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
   ```

## <a name="dns-records-to-be-updated"></a>Enregistrements DNS à mettre à jour

Si votre organisation n’a plus d’utilisateurs hébergés dans Skype Entreprise Server local ou Lync Server, vous devez effectuer les opérations suivantes :

- Mettez à jour la liste des enregistrements DNS Skype Entreprise ci-dessous pour qu’elle pointe vers Microsoft 365 (au lieu du déploiement local). Si vous avez plusieurs domaines SIP, vous devez le faire pour chaque domaine SIP qui est un domaine Microsoft 365 vérifié.

- Supprimez Skype Entreprise enregistrements DNS si le domaine SIP n’est plus utilisé.

Dans chaque domaine où vous trouvez l’un des enregistrements suivants, mettez-les à jour comme suit :

|Type d’enregistrement|Nom|Durée de vie|Priorité|Pondération|Port|Value (Valeur)|
|---|---|---|---|---|---|---|
|SRV|_sipfederationtls._tcp|3600|100|1|5061|sipfed.online.lync.com|
|SRV|_sip._tls|3600|100|1|443|sipdir.online.lync.com|
|CNAME|lyncdiscover|3600|N/A|N/A|S/O|webdir.online.lync.com|
|CNAME|sip|3600|N/A|N/A|S/O|sipdir.online.lync.com|

En outre, les enregistrements CNAME pour la réunion ou la numérotation (le cas échéant) peuvent être supprimés. Enfin, tous les enregistrements DNS pour Skype Entreprise dans votre réseau interne doivent être supprimés.

> [!NOTE]
> Dans de rares cas, le fait de passer du pointage DNS local à Microsoft 365 pour votre organisation peut entraîner l’arrêt du fonctionnement de la fédération avec d’autres organisations jusqu’à ce que cette autre organisation met à jour sa configuration de fédération :
>
> - Toutes les organisations fédérées qui utilisent l’ancien modèle de fédération directe (également appelé serveur partenaire autorisé) devront mettre à jour leurs entrées de domaine autorisées pour que leur organisation supprime le nom de domaine complet du proxy. Ce modèle de fédération hérité n’étant pas basé sur des enregistrements SRV DNS, une telle configuration devient obsolète une fois que votre organisation passe au cloud.
>
> - Toute organisation fédérée qui n’a pas de fournisseur d’hébergement activé pour sipfed.online.lync.<span> com devra mettre à jour sa configuration pour l’activer. Cette situation n’est possible que si l’organisation fédérée est purement locale et n’a jamais été fédérée avec un locataire hybride ou en ligne. Dans ce cas, la fédération avec ces organisations ne fonctionnera pas tant qu’elles n’auront pas activé leur fournisseur d’hébergement.
>
> Si vous pensez que l’un de vos partenaires fédérés utilise la fédération directe ou n’est pas fédéré avec une organisation en ligne ou hybride, nous vous suggérons de leur envoyer une communication à ce sujet lorsque vous vous préparez à effectuer votre migration vers le cloud.
