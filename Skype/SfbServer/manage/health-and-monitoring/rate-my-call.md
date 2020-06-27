---
title: Évaluer mon appel dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Résumé : Découvrez la fonctionnalité taux d’appel dans Skype entreprise Server.'
ms.openlocfilehash: 15f2bcbcf75690baaa350541f5f1da134fb32025
ms.sourcegitcommit: a73df97a06ea860bfaf5387e0acbf3c724697e14
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44902218"
---
# <a name="rate-my-call-in-skype-for-business-server"></a>Évaluer mon appel dans Skype entreprise Server

**Résumé :** En savoir plus sur la fonctionnalité taux d’appel dans Skype entreprise Server.

Taux mon appel était une nouvelle fonctionnalité des clients Skype entreprise 2015 et 2016 sur Windows qui offre aux entreprises un moyen d’obtenir des commentaires de leurs utilisateurs finaux.

La fenêtre taux mon appel offre un système d’évaluation « Star » et des jetons prédéfinis pour les appels audio et vidéo. En outre, les administrateurs peuvent activer un champ personnalisé pour fournir des commentaires.

Taux collecté les données d’appel ne sont pas incluses dans les rapports de surveillance existants, mais elles ont un rapport de surveillance distinct. Les données sont collectées dans des tables SQL accessibles en exécutant des requêtes SQL.

## <a name="rate-my-call-prerequisites"></a>Évaluer les conditions préalables de mes appels

Pour que les utilisateurs de votre déploiement Skype entreprise Server puissent accéder à la fonctionnalité taux d’appel, les composants suivants doivent être déployés et configurés :

-  Skype entreprise Server doit être installé (version 9160 ou ultérieure).

- Demandez à vos utilisateurs d’installer et de mettre à jour la dernière version de Skype entreprise et de leur demander d’utiliser l’interface utilisateur de Skype entreprise.

- Les utilisateurs doivent être hébergés sur le pool frontal Skype entreprise Server.

- Une base de données de surveillance Skype entreprise Server doit être déployée et associée à vos pools Skype entreprise Server.

- Nous vous recommandons de déployer le tableau de bord de qualité des appels (CQD).

## <a name="configure-rate-my-call"></a>Configurer le taux mon appel

La fonctionnalité taux d’appel est activée par défaut dans la stratégie client avec les paramètres suivants :

- Évaluer le pourcentage d’affichage de mon appel-10%

- Évaluer mon appel autoriser un utilisateur personnalisé-désactivé

Aucune action n’est requise pour activer la fonctionnalité de base, mais si vous souhaitez obtenir des commentaires personnalisés, vous devez l’activer séparément. L’applet de commande Windows PowerShell suivante est un exemple d’activation des commentaires personnalisés de l’utilisateur final et de la modification de l’intervalle de 10% à 80%.

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 -RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a>Taux d’accès aux données d’appel

Les données des utilisateurs sont collectées dans deux tables de la base de données de surveillance.

 **[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** -Cette table contient les résultats de l’interrogation des jetons par les utilisateurs finaux.

 **[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** -Cette table contient des définitions de jetons.

Les définitions de jeton sont codées comme suit :

|||
|:-----|:-----|
|1   <br/> |DistortedSpeech  <br/> |
|2   <br/> | ElectronicFeedback <br/> |
|3   <br/> | BackgroundNoise <br/> |
|4   <br/> |MuffledSpeech  <br/> |
|5   <br/> |Écho  <br/> |
| 21  <br/> | FrozenVideo <br/> |
|22,5  <br/> | PixelatedVideo <br/> |
|23  <br/> | BlurryImage <br/> |
|heures/24  <br/> | PoorColor <br/> |
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

 **[QoeMetrics]. [dbo]. [CallQualityFeedback]** Cette table contient les résultats de l’interrogation des commentaires du client et du vote « étoile » s’il est activé.

Les données des tables peuvent être appelées à l’aide d’une requête **Select \* from [table.Name]** ou de Microsoft SQL Server Management Studio.

Les requêtes SQL suivantes peuvent être utilisées :

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

Les derniers clients Skype entreprise signalent de nouveaux ID de jetons de problèmes ( \> 100) qui peuvent ne pas être présents dans votre [QoeMetrics]. [ dbo]. Table [CallQualityFeedbackTokenDef]. Pour mettre à jour la table de base de données avec les dernières définitions de jeton, vous pouvez exécuter la commande SQL ci-dessous sur la base de données de surveillance à l’aide de Microsoft SQL Server Management Studio. Cette commande remplace toutes les entrées du [QoeMetrics]. [dbo]. Table [CallQualityFeedbackTokenDef].

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


