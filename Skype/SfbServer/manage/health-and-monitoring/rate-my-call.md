---
title: Évaluer mon appel dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Résumé : Découvrez la fonctionnalité Évaluer mon appel dans Skype Entreprise Server.'
ms.openlocfilehash: 27fbfa68026feeef54d478ba473961601db0ae8d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390126"
---
# <a name="rate-my-call-in-skype-for-business-server"></a>Évaluer mon appel dans Skype Entreprise Server

**Résumé :** Découvrez la fonctionnalité Évaluer mon appel dans Skype Entreprise Server.

Évaluer mon appel est une nouvelle fonctionnalité des clients Skype Entreprise 2015 et 2016 sur Windows qui permet aux entreprises d’obtenir des commentaires de leurs utilisateurs finaux.

La fenêtre Évaluer mon appel offre un système d’évaluation « étoile » et des jetons prédéfincis pour les appels audio et vidéo. En outre, les administrateurs peuvent activer un champ personnalisé pour fournir des commentaires.

Les données Évaluer mon appel collectées ne sont actuellement incluses dans aucun rapport de surveillance existant, mais elles disposent d’un rapport de surveillance distinct. Les données sont collectées dans SQL tables accessibles en exécutant SQL requêtes.

## <a name="rate-my-call-prerequisites"></a>Évaluer les conditions préalables de mon appel

Pour que les utilisateurs de votre déploiement Skype Entreprise Server peuvent accéder à la fonctionnalité Évaluer mon appel, l’ensemble de composants suivant doit être déployé et configuré :

-  Vous devez avoir Skype Entreprise Server installé (version 9160 ou supérieure).

- Demandez à vos utilisateurs d’installer et de mettre à jour la dernière version de Skype Entreprise et de leur demander d’utiliser l’interface Skype Entreprise utilisateur.

- Les utilisateurs doivent être homed on the Skype Entreprise Server front end pool.

- Une base de données Skype Entreprise Server de surveillance doit être déployée et associée à vos pools Skype Entreprise Server réseau.

- Nous vous recommandons de déployer le Tableau de bord de qualité des appels (CQD).

## <a name="configure-rate-my-call"></a>Configurer Évaluer mon appel

La fonctionnalité Évaluer mon appel est activée par défaut dans la stratégie client avec les paramètres suivants :

- Taux d’affichage de mes appels - 10 %

- Évaluer mon appel autoriser les commentaires des utilisateurs personnalisés - désactivé

Toutefois, aucune action n’est requise pour activer la fonctionnalité de base, mais si vous souhaitez des commentaires personnalisés, vous devrez l’activer séparément. La cmdlet Windows PowerShell suivante est un exemple d’activation des commentaires personnalisés de l’utilisateur final et de la modification de l’intervalle de 10 % à 80 %.

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 -RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a>Accès à Évaluer mes données d’appel

Les données des utilisateurs sont collectées dans deux tables de la base de données de surveillance.

 **[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** - Ce tableau contient les résultats de l’interrogation des jetons par les utilisateurs finaux.

 **[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** - Ce tableau contient les définitions de jeton.

Les définitions de jeton sont codées comme suit :

|#|Définition|
|:-----|:-----|
|1  <br/> |DistortedSpeech  <br/> |
|2  <br/> | ElectronicFeedback <br/> |
|3  <br/> | BackgroundNoise <br/> |
|4  <br/> |MuffledSpeech  <br/> |
|5  <br/> |Écho  <br/> |
| 21  <br/> | FrozenVideo <br/> |
|22  <br/> | PixelatedVideo <br/> |
|23  <br/> | BlurryImage <br/> |
|24  <br/> | PoorColor <br/> |
|25  <br/> | DarkVideo <br/> |
|101  <br/> |Audio_SilentLocal  <br/> |
|102  <br/> |Audio_SilentRemote  <br/> |
|103  <br/> |Audio_Echo  <br/> |
|104  <br/> |Audio_BackgroundNoise  <br/> |
|105  <br/> |Audio_LowSound  <br/> |
|106  <br/> |Audio_Dropped  <br/> |
|107  <br/> |Audio_DistortedSpeech  <br/> |
|108  <br/> |Audio_Interrupted  <br/> |
|109  <br/> |Audio_Other  <br/> |
|201  <br/> |Video_NoLocalVideo  <br/> |
|202  <br/> |Video_NoRemoteVideo  <br/> |
|203  <br/> |Video_LowQuality  <br/> |
|204  <br/> |Video_FrozenVideo  <br/> |
|205  <br/> |Video_StoppedUnexpectedly  <br/> |
|206  <br/> |Video_DarkVideo  <br/> |
|207  <br/> |Video_NoAudioSync  <br/> |
|208  <br/> |Video_Other  <br/> |
|301  <br/> |Pstn_DialPad  <br/> |
|401  <br/> |SS_NoContentLocal  <br/> |
|402  <br/> |SS_NoContentRemote  <br/> |
|403  <br/> |SS_CantPresent  <br/> |
|404  <br/> |SS_LowQuality  <br/> |
|405  <br/> |SS_Freezing  <br/> |
|406  <br/> |SS_StoppedUnexpectedly  <br/> |
|407  <br/> |SS_LargeDelay  <br/> |
|408  <br/> |SS_Other  <br/> |
|501  <br/> |Reliabilty_Join  <br/> |
|502  <br/> |Reliabilty_Invite  <br/> |

 **[QoeMetrics]. [dbo]. [CallQualityFeedback]** Ce tableau contient les résultats des sondages provenant du vote « Star » et des commentaires des clients si activés.

Les données des tables peuvent être **\*** appelées à l’aide d’une requête select à partir de [Table.Name] ou à l’aide de Microsoft SQL Server Management Studio.

Les requêtes SQL suivantes peuvent être utilisées :

 **Audio**

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [AudioStream] AS a WITH (NOLOCK) ON -- only look at Audio related feedback
            a.MediaLineLabel = m.MediaLineLabel    
            and a.ConferenceDateTime = m.ConferenceDateTime 
            and a.SessionSeq = m.SessionSeq
            and a.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
            (CallerCqfToken.TokenId < 20 or (CallerCqfToken.TokenId > 100 and CallerCqfToken.TokenId < 200)) -- only look at Audio related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

 **Video**

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [VideoStream] AS v WITH (NOLOCK) ON -- only look at Video related feedback
            v.MediaLineLabel = m.MediaLineLabel    
            and v.ConferenceDateTime = m.ConferenceDateTime 
            and v.SessionSeq = m.SessionSeq
            and v.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
           ((CallerCqfToken.TokenId > 20 and CallerCqfToken.TokenId < 100) or (CallerCqfToken.TokenId > 200 and CallerCqfToken.TokenId < 300)) -- only look at Video related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

## <a name="updating-token-definitions"></a>Mise à jour des définitions de jeton

Les derniers Skype Entreprise clients signalent de nouveaux ID de jeton de problème (\> 100) qui peuvent ne pas être présents dans votre [QoeMetrics].[ dbo]. Table [CallQualityFeedbackTokenDef]. Pour mettre à jour la table de base de données avec les définitions de jeton les plus récentes, la commande SQL suivante peut être exécuté sur la base de données de surveillance à l’aide Microsoft SQL Server Management Studio. Cette commande remplace toutes les entrées de [QoeMetrics]. [dbo]. Table [CallQualityFeedbackTokenDef].

```SQL
DELETE FROM [CallQualityFeedbackTokenDef];
INSERT INTO [CallQualityFeedbackTokenDef] (TokenId, TokenDescription) VALUES
    (1,   N'DistortedSpeech'),
    (2,   N'ElectronicFeedback'),
    (3,   N'BackgroundNoise'),
    (4,   N'MuffledSpeech'),
    (5,   N'Echo'),
    (21,  N'FrozenVideo'),
    (22,  N'PixelatedVideo'),
    (23,  N'BlurryImage'),
    (24,  N'PoorColor'),
    (25,  N'DarkVideo'),
    (101, N'Audio_SilentLocal'),
    (102, N'Audio_SilentRemote'),
    (103, N'Audio_Echo'),
    (104, N'Audio_BackgroundNoise'),
    (105, N'Audio_LowSound'),
    (106, N'Audio_Dropped'),
    (107, N'Audio_DistortedSpeech'),
    (108, N'Audio_Interrupted'),
    (109, N'Audio_Other'),
    (201, N'Video_NoLocalVideo'),
    (202, N'Video_NoRemoteVideo'),
    (203, N'Video_LowQuality'),
    (204, N'Video_FrozenVideo'),
    (205, N'Video_StoppedUnexpectedly'),
    (206, N'Video_DarkVideo'),
    (207, N'Video_NoAudioSync'),
    (208, N'Video_Other'),
    (301, N'Pstn_DialPad'),
    (401, N'SS_NoContentLocal'),
    (402, N'SS_NoContentRemote'),
    (403, N'SS_CantPresent'),
    (404, N'SS_LowQuality'),
    (405, N'SS_Freezing'),
    (406, N'SS_StoppedUnexpectedly'),
    (407, N'SS_LargeDelay'),
    (408, N'SS_Other'),
    (501, N'Reliabilty_Join'),
    (502, N'Reliabilty_Invite');
```


