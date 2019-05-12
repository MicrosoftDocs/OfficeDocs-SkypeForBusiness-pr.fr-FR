---
title: Taux de mon appel dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Résumé : Découvrez la fonctionnalité appel mon taux dans Skype pour Business Server.'
ms.openlocfilehash: 6b704562d3cfe70b00bc36aff46e509529f9beae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897617"
---
# <a name="rate-my-call-in-skype-for-business-server"></a>Taux de mon appel dans Skype pour Business Server

**Résumé :** Découvrez la fonctionnalité appel mon taux dans Skype pour Business Server.

Taux de mon appel a une nouvelle fonctionnalité de Skype de Business 2015 2016 clients et sur Windows qui permet aux entreprises pour recueillir les commentaires de leurs utilisateurs finaux.

La fenêtre d’appel mon taux offre un système de « étoiles » et les jetons prédéfinis pour les appels audio et vidéos. En outre, les administrateurs peuvent autoriser un champ personnalisé fournir des commentaires.

Les données Évaluer mon appel qui sont collectées ne sont pas incluses dans un rapport de surveillance existant mais font l’objet d’un rapport de surveillance distinct. Collecte des données dans des tables SQL est accessible en exécutant les requêtes SQL.

## <a name="rate-my-call-prerequisites"></a>Configuration requise pour Évaluer mon appel

Avant que les utilisateurs de votre Skype pour le déploiement de serveur d’entreprise puissent accéder appeler mon taux de fonctionnalités, l’ensemble des composants suivants doit être déployée et configurée :

-  Vous devez avoir Skype pour Business Server installé (version 9160 ou ultérieure).

- Demander à vos utilisateurs installer et mettre à jour vers la dernière version de Skype pour les entreprises et également demander à utiliser la Skype pour l’interface utilisateur de l’entreprise.

- Les utilisateurs doivent être hébergés sur le Skype pour Business Server un pool frontal.

- Vous devez avoir un Skype pour Business Server surveillance de base de données déployé et associé à votre Skype pour les pools de serveurs d’entreprise.

- Nous vous recommandons de déployer le Tableau de bord de la qualité des appels (CQD)

## <a name="configure-rate-my-call"></a>Configurer Évaluer mon appel

La fonctionnalité d’appel de mon taux est activée par défaut dans la stratégie du Client avec les paramètres suivants :

- Taux de pourcentage d’affichage mes appels - 10 %

- Taux de mon appel autoriser personnalisé les commentaires des utilisateurs - désactivé

Aucune action n’est requise pour activer la fonctionnalité de base, toutefois, mais si vous souhaitez que les commentaires personnalisé, vous devez l’activer séparément. L’applet de commande Windows PowerShell suivante est un exemple d’activation des commentaires des utilisateurs finaux personnalisées et modification de l’intervalle de 10 % à 80 %.

```
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 - RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a>Accès aux données Évaluer mon appel

Collecte des données des utilisateurs dans les deux tables dans la base de données de surveillance.

 **[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** -Cette table contient les résultats d’émission de jeton d’interrogation par les utilisateurs finaux.

 **[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** -Cette table contient les définitions de jeton.

Les définitions de jetons sont codées ainsi :

|||
|:-----|:-----|
|1  <br/> |DistortedSpeech  <br/> |
|2  <br/> | ElectronicFeedback <br/> |
|3  <br/> | BackgroundNoise <br/> |
|4  <br/> |MuffledSpeech  <br/> |
|5  <br/> |Écho  <br/> |
|21  <br/> | FrozenVideo <br/> |
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

 **[QoeMetrics]. [dbo]. [CallQualityFeedback]** Cette table contient les résultats du sondage à partir des commentaires de client et de vote « Étoile » si activé.

Données issues de tables peuvent être appelées à l’aide d’un **Sélectionnez \* à partir de [Table.Name]** requête ou à l’aide de Microsoft SQL Server Management Studio.

Les requêtes SQL suivantes sont utilisables :

 **Audio**

```
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

```
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

La dernière Skype pour les clients professionnels signaler nouveau jeton problème ID (\> 100) qui ne peuvent pas être présents dans votre [QoeMetrics]. [dbo]. Table [CallQualityFeedbackTokenDef]. Pour mettre à jour la table de base de données avec les dernières définitions de jeton, l’au-dessous SQL commande peut être exécutée sur la base de données de surveillance à l’aide de Microsoft SQL Server Management Studio. Cette commande remplace toutes les entrées de la section [QoeMetrics]. [dbo]. Table [CallQualityFeedbackTokenDef].

```
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


