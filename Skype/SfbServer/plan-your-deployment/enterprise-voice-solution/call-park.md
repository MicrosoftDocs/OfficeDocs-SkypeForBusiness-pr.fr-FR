---
title: Planifier le parc d’appels dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planification du parc d’appels dans Skype entreprise Server Voice, qui permet de mettre les appels en attente et de transférer les appels vers les services. Cela inclut la planification de la capacité, les appels pris en charge et les clients pris en charge.
ms.openlocfilehash: 3effeab4afef60fb7a5021206d9fc3cd0227ceb1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803194"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>Planifier le parc d’appels dans Skype entreprise
 
Planification du parc d’appels dans Skype entreprise Server Voice, qui permet de mettre les appels en attente et de transférer les appels vers les services. Cela inclut la planification de la capacité, les appels pris en charge et les clients pris en charge.
  
L’application de parc d’appel permet aux utilisateurs d’Enterprise Voice d’effectuer les opérations suivantes :
  
- mettre un appel en attente, puis récupérer l’appel depuis le même téléphone ou un autre téléphone ;
    
- mettre un appel en attente pour le transférer vers un service ou une zone générale (par exemple, vers un service commercial ou un entrepôt où il y a un téléphone de partie commune) ;
    
- mettre un appel en attente et garder le téléphone d’origine libre pour répondre aux autres appels.
    
Lorsqu’un utilisateur travaille sur un appel, Skype entreprise Server transfère l’appel vers un numéro temporaire, appelé orbite, où l’appel est maintenu jusqu’à ce qu’il soit récupéré ou qu’il arrive à expiration. Skype entreprise Server envoie l’orbite à l’utilisateur qui a parqué l’appel. Pour récupérer l’appel parqué, l’utilisateur peut composer le numéro de l’orbite ou cliquer sur le lien ou le bouton d’orbite dans la fenêtre de conversation. 
  
L’utilisateur qui a parqué un appel peut avertir quelqu’un pour récupérer l’appel en ayant recours à un mécanisme externe, tel qu’un système de messagerie instantanée ou de radiomessagerie, pour communiquer le numéro d’orbite à quelqu’un d’autre. L’utilisateur qui a parqué l’appel peut laisser la fenêtre de conversation ouverte pour recevoir une notification quand l’appel est récupéré.
  
Étant donné que les plages d’orbites sont globalement uniques, il est possible de récupérer des appels à partir de n’importe quel site Skype entreprise Server ou un téléphone PBX si le routage est configuré de manière appropriée. Si personne ne récupère l’appel dans un délai configurable, la personne qui l’a parqué est rappelée. Si cette personne ne répond pas au rappel, l’appel est transféré vers une destination de remplacement, telle qu’un opérateur, si la configuration est définie de la sorte. Vous pouvez configurer le nombre de sonneries de rappel avant le transfert, de une à dix. Si personne ne répond à un appel transféré, l’appel est déconnecté. L’orbite est libérée lorsque l’appel est récupéré ou déconnecté.
  
Quand vous déployez le parcage d’appel, vous devez réserver des plages de numéros d’extension pour le parcage des appels. Il doit s’agir d’extensions virtuelles, c’est-à-dire d’extensions auxquelles aucun utilisateur ou téléphone n’est attribué. Vous configurez ensuite la table d’orbites de parcage d’appel avec les plages de numéros d’extension, puis spécifiez quel service d’application héberge l’application de parcage d’appel qui gère chaque plage. Chaque pool frontal possède une table de parc d’appels sur le serveur principal correspondant qui est utilisé pour gérer les appels qui sont emparking sur le pool. La liste des plages d’orbites qui est stockée dans le magasin central de gestion est utilisée pour diriger les orbites vers le pool de destination. Chaque pool Skype entreprise Server sur lequel l’application de parc d’appels est déployée et configurée peut avoir une ou plusieurs plages d’orbites. Le déploiement de plages d’orbites doit être globalement unique dans le déploiement de Skype entreprise Server. 
  
Vous configurez également d’autres paramètres de parcage d’appel, tels que l’endroit où sont redirigés les appels s’ils arrivent à expiration et si la personne en ligne entend de la musique lorsque son appel est parqué. Vous pouvez aussi spécifier le fichier de musique à lire lorsque l’appel est en attente.
  
> [!NOTE]
> Les fichiers de conservation de musique personnalisés pour le parc d’appels ne sont pas sauvegardés dans le cadre du processus de reprise après sinistre de Skype entreprise Server et seront perdus si les fichiers téléchargés vers le pool sont endommagés, endommagés ou effacés. Veillez à toujours conserver une copie de sauvegarde distincte des fichiers de mise en attente musicale personnalisés que vous avez téléchargés pour le parcage d’appel. 
  
The Call Park application is a component of Enterprise Voice. Lorsque vous déployez Enterprise Voice, l’application de parc d’appels est installée et activée automatiquement. Pour que vous puissiez utiliser le parc d’appels, vous devez toutefois le configurer et l’activer pour les utilisateurs via la stratégie vocale.
  
## <a name="deployment-and-requirements"></a>Déploiement et exigences

L’application de parc d’appels est automatiquement installée lorsque vous déployez Enterprise Voice. Vous pouvez activer le parc d’appels en configurant une politique vocale.
  
### <a name="software-requirements"></a>Configuration logicielle requise

Tous les serveurs frontaux et les serveurs Standard Edition sur lesquels le parc d’appels est déployé doivent avoir installé le runtime du format Windows Media pour les serveurs exécutant Windows Server 2008 R2 ou Microsoft Media Foundation pour les serveurs exécutant Windows Server 2012 ou Windows Server. 2012 R2. Pour Windows Server 2008 R2, le runtime Windows Media Format Runtime est installé dans le cadre de l’expérience de bureau Windows. Windows Media Format Runtime ou Microsoft Media Foundation est requis pour les fichiers Windows Media audio (. WMA) pour lesquels le parc est lu pour la musique en attente.
  
### <a name="port-requirements"></a>Conditions requises en matière de ports

L’application de parc d’appels utilise le **Port 5075** pour les demandes d’écoute SIP.
    
> [!NOTE]
> Ce port est un paramètre par défaut que vous pouvez modifier à l’aide de l’applet de commande **Set-CsApplicationServer**. Pour plus d’informations sur cette applet de connexion, consultez la documentation Lync Server Management Shell.
  
### <a name="audio-file-requirements"></a>Conditions requises pour les fichiers audio

L’application de parc d’appels prend uniquement en charge les fichiers Windows Media audio (. WMA) pour la musique en attente. Pour personnaliser les fichiers d’attente musicale, vous pouvez utiliser Microsoft Expression Encoder 4. Pour télécharger Expression Encoder 4, voir [« Expression Encoder 4 »](https://go.microsoft.com/fwlink/p/?linkId=202843). Utilisez l’outil pour convertir le fichier au format .wma. Le format recommandé pour les fichiers de la musique de parc d’appels est l’audio multimédia 9, 44 kHz, 16 bits, mono, CBR, 32 kbps.
  
> [!NOTE]
> Le fichier converti est lu sur le téléphone à seulement 16 kHz, même s’il a été enregistré à 44 kHz. 
  
## <a name="supported-clients-and-calls"></a>Types d’appels et clients pris en charge

Les clients et types d’appels suivants sont pris en charge pour le parc d’appels
  
### <a name="clients-supported-for-parking-calls"></a>Clients pris en charge pour le parcage d’appel

Les appels de n’importe quel téléphone IP, PBX (autocommutateur privé), PSTN (réseau téléphonique commuté) ou mobile peuvent être parqués.
  
> [!NOTE]
> Seuls les appels audio peuvent être parqués. Aucun parcage pour les messages instantanés et les conférences n’est possible. 
  
Les clients suivants peuvent utiliser le parc d’appels pour les appels de parc :
  
- Skype Entreprise
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 attendant
    
- Lync Phone Edition
    
> [!NOTE]
> Les téléphones mobiles ne peuvent pas utiliser le parc d’appels pour Park. 
  
### <a name="clients-supported-for-retrieving-calls"></a>Clients pris en charge pour la récupération des appels

Les plages d’orbites sont configurées en tant que blocs de postes virtuels (postes sans utilisateur ou téléphone attribué). Lorsque vous configurez des orbites sous la forme de postes virtuels, les téléphones mobiles et PSTN ne peuvent pas récupérer des appels parqués.
  
Les utilisateurs fédérés ne peuvent pas récupérer des appels parqués.
  
Les clients suivants peuvent récupérer les appels qui sont au parking sur le parc d’appels :
  
- Skype Entreprise
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 attendant
    
- Lync Phone Edition
    
- Téléphones de partie commune IP
    
- Les téléphones non-IP qui sont connectés à l’infrastructure du serveur Skype entreprise, notamment les téléphones portables et les téléphones PBX (Private Branch Exchange);
    
## <a name="call-park-capacity-planning"></a>Planification de capacité pour le parcage d’appel

Le tableau suivant décrit le modèle d’utilisateur de parc d’appels que vous pouvez utiliser comme base pour les exigences de planification de capacité.
  
> [!IMPORTANT]
> Gardez à l’esprit que pour la planification de la capacité de reprise après sinistre, chaque pool d’un pool couplé doit être en mesure de gérer les charges de travail des services de parc d’appels dans les deux pools. 
  
**Modèle utilisateur de parcage d’appel**

|**Mesure**|**Par pool <br/> frontal (avec 8 serveurs frontaux)**|**Par serveur Standard Edition**|
|:-----|:-----|:-----|
|Taux de parcage  <br/> |8 par minute  <br/> |1 par minute  <br/> |
|Taux d’appels parqués récupérés  <br/> |8 par minute  <br/> |1 par minute  <br/> |
|Durée moyenne de parcage  <br/> |60 secondes  <br/> |60 secondes  <br/> |
   

