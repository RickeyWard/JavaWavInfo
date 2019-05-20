# JavaWavInfo
Read RIFF metadata Chunks of WAV files in JAVA
based on wavIO by Evan X. Merz, extended to support more of of the RIFF wav format spec

### Eample Usage
```package testWavInfo;

import com.diamonddrake.wav.InfoTypes;
import com.diamonddrake.wav.WavInfo;

public class App {
	public static void main(String[] args) {
		WavInfo wi = new WavInfo("C:/test.wav");
		System.out.println(wi.getSummary());
		System.out.println(wi.getInfo(InfoTypes.ARTIST));
		System.out.println(wi.getInfo(InfoTypes.COMMENT));
		System.out.println(wi.isIVRFormat());
		
		wi = new WavInfo();
		wi.setPath("C:/test.wav");
		boolean readOK = wi.read();
		if(readOK) {
			System.out.println(wi.getSummary());
			System.out.println(wi.getInfo(InfoTypes.ARTIST));
			System.out.println(wi.getInfo(InfoTypes.COMMENT));
			System.out.println(wi.isIVRFormat());
		}
	}
}
```
