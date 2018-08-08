---
title: Planification de la mise en garde d’appels dans Skype entreprise
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planification de la mise en garde d’appels dans Skype pour Business Server Enterprise Voice, qui permet de placer des appels sur la mise en attente et de transfert d’appels à des services. Cela inclut la planification de la capacité, les appels pris en charge et les clients pris en charge.
ms.openlocfilehash: a675100f8b40e1ab293c0240ea0acbe3beb7fa27
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988549"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>Planification de la mise en garde d’appels dans Skype entreprise
 
Planification de la mise en garde d’appels dans Skype pour Business Server Enterprise Voice, qui permet de placer des appels sur la mise en attente et de transfert d’appels à des services. Cela inclut la planification de la capacité, les appels pris en charge et les clients pris en charge.
  
L’application de parcage d’appel permet aux utilisateurs d’Enterprise Voice effectuer les opérations suivantes :
  
- mettre un appel en attente, puis récupérer l’appel depuis le même téléphone ou un autre téléphone ;
    
- mettre un appel en attente pour le transférer vers un service ou une zone générale (par exemple, vers un service commercial ou un entrepôt où il y a un téléphone de partie commune) ;
    
- mettre un appel en attente et garder le téléphone d’origine libre pour répondre aux autres appels.
    
Lorsqu’un parcs utilisateur un appel Skype pour Business Server transfère l’appel vers un numéro temporaire, appelé une orbite, où l’appel est conservé jusqu'à ce qu’il est extrait ou il arrive à expiration. Skype pour Business Server envoie l’orbite à l’utilisateur qui a été mis en garde l’appel. Pour récupérer l’appel parqué, l’utilisateur peut composer le numéro de l’orbite ou cliquer sur le lien ou le bouton d’orbite dans la fenêtre de conversation. 
  
L’utilisateur qui a parqué un appel peut avertir quelqu’un pour récupérer l’appel en ayant recours à un mécanisme externe, tel qu’un système de messagerie instantanée ou de radiomessagerie, pour communiquer le numéro d’orbite à quelqu’un d’autre. L’utilisateur qui a parqué l’appel peut laisser la fenêtre de conversation ouverte pour recevoir une notification quand l’appel est récupéré.
  
Plages d’orbites étant uniques, il est possible de récupérer des appels à partir de n’importe quel Skype pour site Business Server ou un téléphone PBX si le routage est configuré correctement. Si personne ne récupère l’appel dans un délai configurable, la personne qui l’a parqué est rappelée. Si cette personne ne répond pas au rappel, l’appel est transféré vers une destination de remplacement, telle qu’un opérateur, si la configuration est définie de la sorte. Vous pouvez configurer le nombre de sonneries de rappel avant le transfert, de une à dix. Si personne ne répond à un appel transféré, l’appel est déconnecté. L’orbite est libérée lorsque l’appel est récupéré ou déconnecté.
  
Quand vous déployez le parcage d’appel, vous devez réserver des plages de numéros d’extension pour le parcage des appels. Il doit s’agir d’extensions virtuelles, c’est-à-dire d’extensions auxquelles aucun utilisateur ou téléphone n’est attribué. Vous configurez ensuite la table d’orbites de parcage d’appel avec les plages de numéros d’extension, puis spécifiez quel service d’application héberge l’application de parcage d’appel qui gère chaque plage. Chaque pool frontal possède une table de parcage d’appel sur le correspondant serveur principal qui sert à gérer les appels sont mis en garde dans le pool. La liste des plages d’orbites est stockée dans l’administration centrale stocker et est utilisé pour acheminer des orbites vers le pool de destination. Chaque Skype pour pool Business Server où l’application de parcage d’appel est déployée et configurée peut avoir une ou plusieurs plages d’orbites. Plages d’orbites doivent être globalement uniques dans le Skype pour le déploiement de serveur d’entreprise. 
  
Vous configurez également d’autres paramètres de parcage d’appel, tels que l’endroit où sont redirigés les appels s’ils arrivent à expiration et si la personne en ligne entend de la musique lorsque son appel est parqué. Vous pouvez aussi spécifier le fichier de musique à lire lorsque l’appel est en attente.
  
> [!NOTE]
> Fichiers personnalisés de musique attente parcage d’appel ne sont pas sauvegardées dans le cadre de la Skype pour le processus de récupération d’urgence Business Server et seront perdues si les fichiers téléchargés vers le pool sont endommagées, endommagés ou effacés. Veillez à toujours conserver une copie de sauvegarde distincte des fichiers de mise en attente musicale personnalisés que vous avez téléchargés pour le parcage d’appel. 
  
L’application de parcage d’appel est un composant d’Enterprise Voice. Lorsque vous déployez Enterprise Voice, l’application de parcage d’appel est installée et activée automatiquement. Toutefois, avant de pouvoir utiliser le parcage d’appel, l’administrateur Enterprise Voice doit configurer et activer des utilisateurs par le biais de la stratégie de voix.
  
## <a name="deployment-and-requirements"></a>Déploiement et configuration requise

L’application de parcage d’appel est automatiquement installée lorsque vous déployez Enterprise Voice. Configuration de la stratégie de voix activer la mise en garde d’appels.
  
### <a name="software-requirements"></a>Configuration logicielle requise

Les serveurs de tous les serveurs frontaux et Standard Edition où la mise en garde d’appels est déployée doivent disposer de Windows Media Format Runtime installé pour les serveurs exécutant Windows Server 2008 R2 ou Microsoft Media Foundation pour les serveurs exécutant Windows Server 2012 ou Windows Server 2012 R2. Pour Windows Server 2008 R2, le module d’exécution du Format Windows Media est installé dans le cadre de l’expérience de bureau Windows. Module d’exécution du Format Windows Media ou Microsoft Media Foundation est requise pour l’Audio Windows Media (.wma) fichiers qui joue le parcage d’appel de la musique en attente.
  
### <a name="port-requirements"></a>Conditions requises en matière de ports

L’application de parcage d’appel utilise **le Port 5075** pour les demandes d’écoute SIP.
    
> [!NOTE]
> Ce port est un paramètre par défaut que vous pouvez modifier à l’aide de l’applet de commande **Set-CsApplicationServer** . Pour plus d’informations sur cette applet de commande, voir la documentation de Lync Server Management Shell.
  
### <a name="audio-file-requirements"></a>Conditions requises pour les fichiers audio

L’application prend en charge uniquement les fichiers Audio Windows Media (.wma) de la musique sur le parcage d’appel en attente. Pour personnaliser les fichiers d’attente musicale, vous pouvez utiliser Microsoft Expression Encoder 4. Pour télécharger Expression Encoder 4, voir [« Expression Encoder 4 »](https://go.microsoft.com/fwlink/p/?linkId=202843). Utilisez l’outil pour convertir le fichier au format .wma. Le format recommandé pour les fichiers de musique en attente de parcage d’appel est Media Audio 9, 44 kHz, 16 bits Mono, CBR, 32 Kbits/s.
  
> [!NOTE]
> Le fichier converti est lu sur le téléphone à seulement 16 kHz, même s’il a été enregistré à 44 kHz. 
  
## <a name="supported-clients-and-calls"></a>Types d’appels et clients pris en charge

Les clients et les types d’appels suivants sont pris en charge pour la mise en garde d’appels
  
### <a name="clients-supported-for-parking-calls"></a>Clients pris en charge pour le parcage d’appel

Les appels de n’importe quel téléphone IP, PBX (autocommutateur privé), PSTN (réseau téléphonique commuté) ou mobile peuvent être parqués.
  
> [!NOTE]
> Seuls les appels audio peuvent être parqués. Aucun parcage pour les messages instantanés et les conférences n’est possible. 
  
Les clients suivants permet de parcage d’appel parquer des appels :
  
- Skype Entreprise
    
- Lync 2013
    
- Lync 2010
    
- Intendant Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Téléphones mobiles ne pouvez pas utiliser la mise en garde d’appels recours. 
  
### <a name="clients-supported-for-retrieving-calls"></a>Clients pris en charge pour la récupération des appels

Les plages d’orbites sont configurées en tant que blocs de postes virtuels (postes sans utilisateur ou téléphone attribué). Lorsque vous configurez des orbites sous la forme de postes virtuels, les téléphones mobiles et PSTN ne peuvent pas récupérer des appels parqués.
  
Les utilisateurs fédérés ne peuvent pas récupérer des appels parqués.
  
Les clients suivants peuvent récupérer des appels qui sont mis en garde dans la mise en garde d’appels :
  
- Skype Entreprise
    
- Lync 2013
    
- Lync 2010
    
- Intendant Lync 2010
    
- Lync Phone Edition
    
- Téléphones de partie commune IP
    
- Téléphones non IP connectés à la Skype pour infrastructure Business Server, y compris les téléphones de partie commune et des téléphones autocommutateur privé (PBX) exchange
    
## <a name="call-park-capacity-planning"></a>Planification de capacité pour le parcage d’appel

Le tableau suivant décrit le modèle utilisateur de parcage d’appel que vous pouvez utiliser comme base pour les exigences de planification de capacité.
  
> [!IMPORTANT]
> N’oubliez pas que, pour la planification de la capacité la récupération d’urgence, chaque pool d’un pool associé doit être en mesure de gérer les charges de travail pour les services de parcage d’appel dans les deux pools. 
  
**Modèle utilisateur de parcage d’appel**

|**Mesure**|**Par pool frontal <br/> (avec 8 serveurs frontaux)**|**Par serveur Standard Edition**|
|:-----|:-----|:-----|
|Taux de parcage  <br/> |8 par minute  <br/> |1 par minute  <br/> |
|Taux d’appels parqués récupérés  <br/> |8 par minute  <br/> |1 par minute  <br/> |
|Durée moyenne de parcage  <br/> |60 secondes  <br/> |60 secondes  <br/> |
   

