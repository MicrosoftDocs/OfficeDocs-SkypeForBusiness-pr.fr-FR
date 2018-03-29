---
title: Planification du parcage d’appel dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planification de parc d’appel dans Skype pour Business Server Voix Entreprise, qui permet de placer des appels bloqués et transférez des appels aux services. Cela inclut la planification de la capacité, les appels pris en charge et les clients pris en charge.
ms.openlocfilehash: 6198b54a93c36c2e6a2fcd28fa91f51c43fb59de
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-call-park-in-skype-for-business-2015"></a>Planification du parcage d’appel dans Skype Entreprise 2015
 
Planification de parc d’appel dans Skype pour Business Server Voix Entreprise, qui permet de placer des appels bloqués et transférez des appels aux services. Cela inclut la planification de la capacité, les appels pris en charge et les clients pris en charge.
  
L’application d’appel Park permet aux utilisateurs de Voix Entreprise effectuer les opérations suivantes :
  
- mettre un appel en attente, puis récupérer l’appel depuis le même téléphone ou un autre téléphone ;
    
- mettre un appel en attente pour le transférer vers un service ou une zone générale (par exemple, vers un service commercial ou un entrepôt où il y a un téléphone de partie commune) ;
    
- mettre un appel en attente et garder le téléphone d’origine libre pour répondre aux autres appels.
    
Lorsque les parcs à un utilisateur un appel, Skype pour Business Server transfère l’appel vers un numéro temporaire, appelé une orbite, où l’appel est maintenu jusqu'à ce qu’il est extrait ou il arrive à expiration. Skype pour Business Server envoie l’orbite à l’utilisateur qui stationnés de l’appel. Pour récupérer l’appel parqué, l’utilisateur peut composer le numéro de l’orbite ou cliquer sur le lien ou le bouton d’orbite dans la fenêtre de conversation. 
  
L’utilisateur qui a parqué un appel peut avertir quelqu’un pour récupérer l’appel en ayant recours à un mécanisme externe, tel qu’un système de messagerie instantanée ou de radiomessagerie, pour communiquer le numéro d’orbite à quelqu’un d’autre. L’utilisateur qui a parqué l’appel peut laisser la fenêtre de conversation ouverte pour recevoir une notification quand l’appel est récupéré.
  
Car les plages d’orbite sont globalement uniques, il est possible de récupérer des appels à partir de n’importe quel Skype pour site Business Server ou le téléphone PBX si le routage est configuré correctement. Si personne ne récupère l’appel dans un délai configurable, la personne qui l’a parqué est rappelée. Si cette personne ne répond pas au rappel, l’appel est transféré vers une destination de remplacement, telle qu’un opérateur, si la configuration est définie de la sorte. Vous pouvez configurer le nombre de sonneries de rappel avant le transfert, de une à dix. Si personne ne répond à un appel transféré, l’appel est déconnecté. L’orbite est libérée lorsque l’appel est récupéré ou déconnecté.
  
Quand vous déployez le parcage d’appel, vous devez réserver des plages de numéros d’extension pour le parcage des appels. Il doit s’agir d’extensions virtuelles, c’est-à-dire d’extensions auxquelles aucun utilisateur ou téléphone n’est attribué. Vous configurez ensuite la table d’orbites de parcage d’appel avec les plages de numéros d’extension, puis spécifiez quel service d’application héberge l’application de parcage d’appel qui gère chaque plage. Chaque pool frontal comporte une table de parc d’appel sur le correspondant serveur principal qui est utilisé pour gérer les appels qui sont stationnés sur le pool. La liste de plages d’orbite est stockée dans la direction centrale stocker et est utilisé pour router des orbites vers le pool de destination. Chaque Skype pour le pool de serveur de l’entreprise où l’application d’appel Park est déployée et configurée peut avoir une ou plusieurs plages d’orbite. Plages d’orbite doivent être globalement uniques sur le Skype pour le déploiement du serveur de l’entreprise. 
  
Vous configurez également d’autres paramètres de parcage d’appel, tels que l’endroit où sont redirigés les appels s’ils arrivent à expiration et si la personne en ligne entend de la musique lorsque son appel est parqué. Vous pouvez aussi spécifier le fichier de musique à lire lorsque l’appel est en attente.
  
> [!NOTE]
> Les fichiers de musique en attente personnalisés pour le parc de l’appel ne sont pas sauvegardés dans le cadre de la Skype pour le processus de récupération après sinistre Business Server et seront perdues si les fichiers téléchargés vers le pool sont endommagés, endommagés ou effacés. Veillez à toujours conserver une copie de sauvegarde distincte des fichiers de mise en attente musicale personnalisés que vous avez téléchargés pour le parcage d’appel. 
  
L’application d’appel Park est un composant de Voix Entreprise. Lors du déploiement de Voix Entreprise, l’application d’appel Park est installée et activée automatiquement. Avant de pouvoir utiliser appel Park, toutefois, l’administrateur de Voix Entreprise doit le configurer et l’activer pour les utilisateurs via la stratégie voice.
  
## <a name="deployment-and-requirements"></a>Déploiement et configuration requise

L’application d’appel Park est automatiquement installée lors du déploiement de Voix Entreprise. Vous activez le parc d’appel en configurant la stratégie voice.
  
### <a name="software-requirements"></a>Configuration logicielle requise

Les serveurs de tous les serveurs frontaux et Standard Edition où est déployé le parc de l’appel doivent être Windows Media Format Runtime installé pour les serveurs exécutant Windows Server 2008 R2, ou Microsoft Media Foundation pour les serveurs exécutant Windows Server ou Windows Server 2012 2012 R2. Pour Windows Server 2008 R2, Windows Media Format Runtime est installé dans le cadre de l’expérience utilisateur Windows. Windows Media Format Runtime ou Microsoft Media Foundation est requise pour Windows Media Audio (.wma) fichiers appel Park joue de la musique en attente.
  
### <a name="port-requirements"></a>Conditions requises en matière de ports

L’application d’appel Park utilise le **Port 5075** pour les requêtes d’écoute SIP.
    
> [!NOTE]
> Ce port est un paramètre par défaut que vous pouvez modifier à l’aide de l’applet de commande **Set-CsApplicationServer** . Pour plus d’informations sur cette applet de commande, consultez la documentation de Communications Server Management Shell.
  
### <a name="audio-file-requirements"></a>Conditions requises pour les fichiers audio

Le parc d’appel application prend en charge uniquement les fichiers Audio Windows Media (.wma) de la musique sur Maintenez. Pour personnaliser les fichiers d’attente musicale, vous pouvez utiliser Microsoft Expression Encoder 4. Pour télécharger Microsoft Expression Encoder 4, consultez [« Expression Encoder 4 »](https://go.microsoft.com/fwlink/p/?linkId=202843). Utilisez l’outil pour convertir le fichier au format .wma. Le format recommandé pour les fichiers de musique en attente d’appel Park est Media Audio 9, 44 kHz, 16 bits Mono, CBR, 32 Kbits/s.
  
> [!NOTE]
> Le fichier converti est lu sur le téléphone à seulement 16 kHz, même s’il a été enregistré à 44 kHz. 
  
## <a name="supported-clients-and-calls"></a>Types d’appels et clients pris en charge

Les clients et les types d’appels suivants sont pris en charge pour le parc de l’appel
  
### <a name="clients-supported-for-parking-calls"></a>Clients pris en charge pour le parcage d’appel

Les appels de n’importe quel téléphone IP, PBX (autocommutateur privé), PSTN (réseau téléphonique commuté) ou mobile peuvent être parqués.
  
> [!NOTE]
> Seuls les appels audio peuvent être parqués. Aucun parcage pour les messages instantanés et les conférences n’est possible. 
  
Les clients suivants permettent appel Park park appels :
  
- Skype Entreprise
    
- Lync 2013
    
- Lync 2010
    
- Intendant Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Téléphones mobiles ne permet pas appel Park park appels. 
  
### <a name="clients-supported-for-retrieving-calls"></a>Clients pris en charge pour la récupération des appels

Les plages d’orbites sont configurées en tant que blocs de postes virtuels (postes sans utilisateur ou téléphone attribué). Lorsque vous configurez des orbites sous la forme de postes virtuels, les téléphones mobiles et PSTN ne peuvent pas récupérer des appels parqués.
  
Les utilisateurs fédérés ne peuvent pas récupérer des appels parqués.
  
Les clients suivants peuvent récupérer les appels qui sont stationnés sur le parc de l’appel :
  
- Skype Entreprise
    
- Lync 2013
    
- Lync 2010
    
- Intendant Lync 2010
    
- Lync Phone Edition
    
- Téléphones de partie commune IP
    
- Les téléphones IP non connectés à la Skype pour l’infrastructure de serveur d’entreprise, y compris les téléphones de zone courants et des téléphones private branch exchange (PBX)
    
## <a name="call-park-capacity-planning"></a>Planification de capacité pour le parcage d’appel

Le tableau suivant décrit le modèle d’appel Park utilisateur que vous pouvez utiliser comme base pour la planification de capacité.
  
> [!IMPORTANT]
> Gardez à l’esprit que, pour la planification de capacité la récupération après sinistre, chaque pool d’un pool de paires devrait être en mesure de gérer les charges de travail pour les services d’appel Park dans les deux pools. 
  
**Modèle d’utilisateur appel Park**

|**Métrique**|**Par pool frontal <br/> (avec 8 serveurs frontaux)**|**Par serveur Standard Edition server**|
|:-----|:-----|:-----|
|Taux de parcage  <br/> |8 par minute  <br/> |1 par minute  <br/> |
|Taux d’appels parqués récupérés  <br/> |8 par minute  <br/> |1 par minute  <br/> |
|Durée moyenne de parcage  <br/> |60 secondes  <br/> |60 secondes  <br/> |
   

