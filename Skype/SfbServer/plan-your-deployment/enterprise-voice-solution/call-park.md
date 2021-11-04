---
title: Planifier le parc d’appel dans Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planification du parcage d’appel Skype Entreprise Server Voix Entreprise, qui permet de mettre les appels en attente et de transférer des appels vers des services. Inclut la planification de capacité, les appels pris en charge et les clients pris en charge.
ms.openlocfilehash: 1cba225d966f835e59f75c359cee49ab183d21eb
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60770182"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>Planifier le parc d’appel dans Skype Entreprise
 
Planification du parcage d’appel Skype Entreprise Server Voix Entreprise, qui permet de mettre les appels en attente et de transférer des appels vers des services. Inclut la planification de capacité, les appels pris en charge et les clients pris en charge.
  
L’application de parcage d Voix Entreprise permet aux utilisateurs d’appliquer les mesures suivantes :
  
- Mettez un appel en attente, puis récupérez l’appel à partir du même téléphone ou d’un autre téléphone.
    
- Mettre un appel en attente pour le transférer vers un service ou une zone générale (par exemple, vers un service commercial ou un entrepôt où se trouve un téléphone de partie commune).
    
- Mettez un appel en attente et maintenez le téléphone de répondage d’origine gratuit pour les autres appels.
    
Lorsqu’un utilisateur parlait un appel, Skype Entreprise Server transfère l’appel vers un numéro temporaire, appelé orbite, où l’appel est mis en attente jusqu’à ce qu’il soit récupéré ou qu’il n’sorte pas. Skype Entreprise Server l’orbite à l’utilisateur qui a par parcé l’appel. Pour récupérer l’appel par parcé, l’utilisateur peut composer le numéro d’orbite ou cliquer sur le lien ou le bouton d’orbite dans la fenêtre de conversation. 
  
L’utilisateur qui a par parcé un appel peut avertir quelqu’un de récupérer l’appel à l’aide d’un mécanisme externe, tel que la messagerie instantanée ou un système de pagination, pour communiquer le numéro d’orbite à une autre personne. L’utilisateur qui a paré l’appel peut laisser la fenêtre de conversation ouverte pour recevoir une notification lorsque l’appel est récupéré.
  
Étant donné que les plages d’orbites sont globalement uniques, il est possible de récupérer des appels à partir d’un site Skype Entreprise Server ou d’un téléphone PBX si le routage est configuré correctement. Si personne ne récupère l’appel dans un laps de temps configurable, l’appel revient à la personne qui l’a par parcé. Si cette personne ne répond pas à la sonnerie, l’appel est transféré vers une destination de récupération, par exemple un opérateur, si tel est le cas. Vous pouvez configurer le nombre de sonneries de l’appel avant d’être transféré d’une à dix fois. Si personne ne répond à un appel transféré, l’appel est déconnecté. L’orbite est libérée lorsque l’appel est récupéré ou déconnecté.
  
Lorsque vous déployez le parcier d’appel, vous devez réserver des plages de numéros de poste pour le parc d’appels. Ces extensions doivent être des extensions virtuelles : les extensions qui n’ont pas d’utilisateur ou de téléphone qui leur sont affectés. Vous configurez ensuite la table des orbites de parcage d’appel avec les plages de numéros de poste et spécifiez le service d’application qui héberge l’application de parcage d’appel qui gère chaque plage. Chaque pool frontal dispose d’une table de parcage d’appel sur le serveur principal correspondant qui est utilisée pour gérer les appels parés sur le pool. La liste des plages d’orbites est stockée dans le magasin central de gestion et sert à router les orbites vers le pool de destination. Chaque Skype Entreprise Server pool dans lequel l’application de parcage d’appel est déployée et configurée peut avoir une ou plusieurs plages d’orbites. Les plages d’orbites doivent être globalement uniques dans Skype Entreprise Server déploiement. 
  
Vous configurez également d’autres paramètres de parcment d’appel, tels que l’endroit où les appels sont redirigés s’ils sont à l’heure d’inextérable et si la personne qui se trouve sur le téléphone entend de la musique pendant qu’elle est parée. Vous pouvez également spécifier le fichier de musique à lire pendant l’attente de l’appel.
  
> [!NOTE]
> Les fichiers d’attente musicale personnalisés pour le parcage d’appel ne sont pas pris en charge dans le cadre du processus de récupération d’urgence Skype Entreprise Server et seront perdus si les fichiers chargés dans le pool sont endommagés, endommagés ou effacés. Conservez toujours une copie de sauvegarde distincte des fichiers d’attente musicale personnalisés que vous avez téléchargés pour le parcement d’appel. 
  
L’application de parcage d’appel est un composant de Voix Entreprise. Lorsque vous déployez Voix Entreprise, l’application de parcage d’appel est installée et activée automatiquement. Toutefois, avant de pouvoir utiliser le parcier d’appel, l’administrateur Voix Entreprise doit le configurer et l’activer pour les utilisateurs via la stratégie de voix.
  
## <a name="deployment-and-requirements"></a>Déploiement et conditions requises

L’application de parcage d’appel est installée automatiquement lorsque vous déployez Voix Entreprise. Vous activez le parcage d’appel en configurant la stratégie de voix.
  
### <a name="software-requirements"></a>Configuration logicielle requise

Le runtime du format multimédia Windows doit être installé sur tous les serveurs frontaux et serveurs Édition Standard sur lequel le parcage d’appel est déployé pour les serveurs exécutant Windows Server 2008 R2 ou Microsoft Media Foundation pour les serveurs exécutant Windows Server 2012 ou Windows Server 2012 R2 . Pour Windows Server 2008 R2, le Windows du format multimédia est installé dans le cadre de Windows Expérience utilisateur. Windows Media Format Runtime ou Microsoft Media Foundation est requis pour les fichiers Windows Media Audio (.wma) que le parcage d’appel lit pendant l’attente musicale.
  
### <a name="port-requirements"></a>Conditions requises en matière de ports

L’application de parcage d’appel **utilise le port 5075 pour**  les demandes d’écoute SIP.
    
> [!NOTE]
> Ce port est un paramètre par défaut que vous pouvez modifier à l’aide de l’applet de commande **Set-CsApplicationServer**. Pour plus d’informations sur cette cmdlet, voir la documentation de Lync Server Management Shell.
  
### <a name="audio-file-requirements"></a>Conditions requises pour les fichiers audio

L’application de parcage d’appel Windows uniquement les fichiers audio multimédias (.wma) pour l’attente musicale. Pour personnaliser les fichiers d’attente musicale, vous pouvez utiliser Microsoft Expression Encoder 4. Pour télécharger Expression Encoder 4, voir   [« Expression Encoder 4](https://go.microsoft.com/fwlink/p/?linkId=202843)». Utilisez l’outil pour convertir le fichier au format .wma. Le format recommandé des fichiers d’attente musicale pour le parcage d’appel est Windows Media Audio 9,44 kHz, 16 bits, Mono, CBR, 32 Kbits/s.
  
> [!NOTE]
> Le fichier converti est lu à 16 kHz sur le téléphone, même s’il a été enregistré à 44 kHz. 
  
## <a name="supported-clients-and-calls"></a>Appels et clients pris en charge

Les clients et types d’appels suivants sont pris en charge pour le parc d’appel
  
### <a name="clients-supported-for-parking-calls"></a>Clients pris en charge pour le parcage d’appel

Les appels de n’importe quel téléphone IP, PBX (autocommutateur privé), RTC (réseau téléphonique commuté) ou mobile peuvent être parqués.
  
> [!NOTE]
> Seuls les appels audio peuvent être parqués. Aucun parcage pour les messages instantanés et les conférences n’est possible. 
  
Les clients suivants peuvent utiliser le parcier d’appel pour parer les appels :
  
- Skype Entreprise
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
> [!NOTE]
> Les téléphones mobiles ne peuvent pas utiliser le parcier d’appel pour parer les appels. 
  
### <a name="clients-supported-for-retrieving-calls"></a>Clients pris en charge pour la récupération des appels

Les plages d’orbites sont configurées en tant que blocs de postes virtuels (postes sans utilisateur ou téléphone attribué). Lorsque vous configurez des orbites sous la forme de postes virtuels, les téléphones mobiles et RTC ne peuvent pas récupérer des appels parqués.
  
Les utilisateurs fédérés ne peuvent pas récupérer des appels parqués.
  
Les clients suivants peuvent récupérer les appels par parcés sur le parc d’appel :
  
- Skype Entreprise
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
- Téléphones de partie commune IP
    
- Téléphones non IP connectés à l’infrastructure Skype Entreprise Server, y compris les téléphones de partie commune et les téléphones PBX
    
## <a name="call-park-capacity-planning"></a>Planification de la capacité du parcier d’appel

Le tableau suivant décrit le modèle utilisateur du parc d’appel que vous pouvez utiliser comme base pour les besoins de planification de la capacité.
  
> [!IMPORTANT]
> N’oubliez pas que, pour la planification de la capacité de récupération d’urgence, chaque pool d’un pool couplé doit être en mesure de gérer les charges de travail des services de parcage d’appel dans les deux pools. 
  
**Modèle utilisateur de parcage d’appel**

|**Métrique**|**Par pool frontal  <br/>  (avec 8 serveurs frontux)**|**Par serveur Standard Edition**|
|:-----|:-----|:-----|
|Taux de parcage  <br/> |8 par minute  <br/> |1 par minute  <br/> |
|Taux d’appels parqués récupérés  <br/> |8 par minute  <br/> |1 par minute  <br/> |
|Durée moyenne de parcage  <br/> |60 secondes  <br/> |60 secondes  <br/> |
   

