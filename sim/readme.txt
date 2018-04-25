To simulate E2, rename the simhwE2.xml to simhw.xml. Relaunch simulator
To simulate E2-Jr, rename the simhwE2JR.xml to simhw.xml. Relaunch simulator
To simulate S34K, rename the simhwS3.xml to simhw.xml. Relaunch simulator
To simulate S34K-Jr, rename the simhwS3JR.xml to simhw.xml. Relaunch simulator
To simulate EX, rename the simhwEX.xml to simhw.xml. Relaunch simulator

---
To simulate EX connections to E2 or S3, add the following in the simhw.xml of an E2 or S3.
Example below simulates that there is a link cable connected to the Link card in Slot 1, Connector 2.
On that connector, there is an EX with Unit ID 3, IP address 192.168.0.180 and MAC 94:65:9c:6c:ad:ac

<linkinfo 
   selfslot="0" 
   selfconn="1"  
   detectframetype="2" 
   detectslot="0" 
   detectsconn="1" 
   detectunitid="3" 
   detectip="192.168.0.180" 
   detectmac="94:65:9c:6c:ad:ac" >
</linkinfo>

Explanations below

Self Info
 * selfslot – connector belonging to which slot index. 1st slot is 0
 * selfconn - self connector index ( 0 or 1, first connector or second connector)

Frame Detected Info
 * detectframetype – the type of the frame which the connector detects. (0 = E2, 1 = S3, 2 = EX)
 * detectslot – to which slot index of the frame detected is link connector connected to.  1st slot is slot index 0
 * detectconn – to which connector index of the frame detected  is link connector connected to. 1st connector is connector index 0
 * detectunitid – the frame detected unit id
 * detectip – the frame detected IP address
 * detectmac – the frame detected MAC address

Example below is a simhw.xml for E2 with a EX on each of the 4 Link card connectors

<simhw> 
   <frametype type="0"></frametype>
   <card id="thisissometextforid0" type="70" slot="0">CardType_Exp</card>
   <card id="thisissometextforid1" type="70" slot="1">CardType_Exp</card>
   <card id="thisissometextforid210" type="1" slot="2">CardType_Input_4_SDI</card>
   <card id="thisissometextforid211" type="1" slot="3">CardType_Input_4_SDI</card>
   <card id="thisissometextforid3" type="0" slot="4">CardType_Input_2_DVI</card>
   <card id="thisissometextforid4" type="0" slot="5">CardType_Input_2_DVI</card>
   <card id="thisissometextforid5" type="2" slot="6">CardType_Input_4_HDMI_DP</card>
   <card id="thisissometextforid7" type="2" slot="7">CardType_Input_4_HDMI_DP</card>
   <card id="thisissometextforid8" type="2" slot="8">CardType_Input_4_HDMI_DP</card>
   <card id="thisissometextforid9" type="2" slot="9">CardType_Input_4_HDMI_DP</card>
   <card id="CardID3" type="22" slot="10">CardType_Output_4_HDMI</card> 
   <card id="CardID4" type="22" slot="11">CardType_Output_4_HDMI</card>
   <card id="CardID415" type="21" slot="12">CardType_Output_4_SDI</card>
   <card id="CardID15" type="40" slot="13">CardType_Output_Multiviewer</card>
   <card id="thisissometextforid501" type="50" slot="14">CardType_VPU</card>
   <card id="thisissometextforid502" type="50" slot="15">CardType_VPU</card>
   <card id="thisissometextforid503" type="50" slot="16">CardType_VPU</card>
   <card id="thisissometextforid504" type="50" slot="17">CardType_VPU</card>
   <card id="thisissometextforid505" type="50" slot="19">CardType_VPU</card>
   <card id="thisissometextforid506" type="50" slot="20">CardType_VPU</card>
   <card id="thisissometextforid507" type="50" slot="21">CardType_VPU</card>
   <card id="thisissometextforid508" type="50" slot="22">CardType_VPU</card>   
   <linkinfo selfslot="0" selfconn="0" detectframetype="2" detectslot="0" detectsconn="1" detectunitid="3" detectip="192.168.0.180" detectmac="94:65:9c:6c:ad:ac" > </linkinfo>
   <linkinfo selfslot="0" selfconn="1" detectframetype="2" detectslot="0" detectsconn="1" detectunitid="3" detectip="192.168.0.181" detectmac="94:65:9c:6c:ad:bc" > </linkinfo>
   <linkinfo selfslot="1" selfconn="0" detectframetype="2" detectslot="0" detectsconn="1" detectunitid="3" detectip="192.168.0.182" detectmac="94:65:9c:6c:ad:dc" > </linkinfo>
   <linkinfo selfslot="1" selfconn="1" detectframetype="2" detectslot="0" detectsconn="1" detectunitid="3" detectip="192.168.0.183" detectmac="94:65:9c:6c:ad:ec" > </linkinfo>
</simhw>
